---
id: gen-ai/ai-incident-response-playbook
title: "AI Incident Response: The Playbook Your Team Does Not Have"
sidebar_label: AI Incident Response
previous_page: gen-ai/ai-observability-llm-monitoring-production
next_page: gen-ai/ai-sre
---

<div style="text-align: right;">
    <a href="https://kranthib.github.io/tech-pulse/" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Back to Home →</a>
</div>

---

# AI Incident Response: The Playbook Your Team Does Not Have

**Why the runbooks written for traditional software failures will leave your AI systems exposed — and what to build before the next incident arrives.**

![0000](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ai-incident-response/0000.png)

---

## The Call That Changes Everything

It was a Tuesday morning when the support queue started flooding. Not with errors. Not with timeouts. With something harder to classify: users reporting that the AI-assisted recommendations they had acted on were wrong. Systematically, confidently, plausibly wrong.

The infrastructure dashboard showed green. Latency was nominal. Error rates were flat. The model was running. From every instrument the team had wired up, the system was healthy.

It took four hours to confirm that the retrieval pipeline had silently degraded two days earlier after a routine index update. The model had continued generating responses throughout — coherent, well-formatted, contextually plausible responses built on retrieved context that was subtly but consistently incorrect. Users had made purchasing decisions, submitted forms, and routed work based on those responses.

This is not a hypothetical. Variations of this failure have played out at organizations that had monitoring in place, had passed security reviews, and had experienced engineering teams. The gap was not in their infrastructure. It was in their incident response playbook. They had built runbooks for systems that fail noisily. They were running a system that fails silently.

This post is about building the playbook before you need it.

---

## Why AI Incidents Break Traditional Runbooks

Traditional incident response is built on a foundational assumption: failures are detectable. A service crashes, a timeout fires, an exception propagates, an alert triggers. The failure is loud, binary, and observable through standard instrumentation. The incident commander knows an incident is occurring because the monitors say so.

AI systems break this assumption completely.

![0001](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ai-incident-response/0001.png)

Consider what happens when a large language model begins hallucinating at elevated rates. The service does not crash. The API does not return error codes. Response latency does not spike. The model continues generating outputs that look exactly like correct outputs — same formatting, same confidence, same apparent coherence. The only signal is semantic: the content is wrong. And semantic correctness is not something a traditional APM tool measures.

Or consider an agent that begins taking actions slightly outside its intended scope. Not dramatically wrong actions that would trigger a hard stop. Slightly wrong actions — querying tables it should not touch, writing data to a field that was not in the original specification, passing parameters to a downstream service in a format that technically succeeds but produces unintended side effects. The agent is running. The tools are responding. The logs show successful executions. The incident is invisible to every instrument except one that understands what the correct behavior should have been.

There are four structural differences between AI failures and traditional software failures that every incident response playbook must account for:

**Silent failures versus noisy failures.** Traditional systems fail with exceptions, timeouts, and crash reports. AI systems fail with confident wrong outputs. The monitoring strategy must be able to detect semantic incorrectness, not just operational unavailability.

**Probabilistic outputs versus deterministic behavior.** When a traditional service misbehaves, you can often reproduce the failure deterministically and trace it to a specific code path. When an AI system misbehaves, the same input may produce different outputs across runs. Root cause analysis cannot follow the same path.

**Multi-hop causality in agentic systems.** A single agent action may trigger tool calls, memory retrievals, and downstream agent invocations. When something goes wrong, the causal chain spans multiple hops, multiple services, and potentially multiple model invocations. Tracing that chain requires instrumentation that propagates context across every hop.

**Model version as a hidden variable.** In traditional systems, the code version is explicit and auditable. In AI systems, the effective behavior of the system depends on the interaction of model version, prompt version, retrieval context, and runtime parameters — any of which can change and any of which can be the source of an incident. Rollback is not a single operation.

These differences do not mean that AI systems cannot be operated reliably. They mean that operating them reliably requires a different class of runbook.

---

## The Five AI-Specific Failure Modes

Through direct experience managing AI systems in production and analyzing incidents across the industry, I have identified five failure modes that appear repeatedly and that traditional runbooks consistently fail to address. Understanding each — its mechanics, its signals, and its blast radius — is the prerequisite for building effective response protocols.

![0002](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ai-incident-response/0002.png)

### Failure Mode 1: Hallucination Spikes

A hallucination spike is a sudden, statistically significant increase in the rate at which a model generates factually incorrect or fabricated outputs. This can be triggered by a model version update, a change in the system prompt that alters the model's reasoning pattern, a distribution shift in input data, or retrieval context that introduces contradictory or out-of-domain information.

The signal that distinguishes a hallucination spike from baseline hallucination rate is statistical: the rate changes, not just the presence. Every production language model hallucinates at some baseline frequency. The incident occurs when that rate crosses a threshold that begins affecting user outcomes at scale.

Detection requires sampling-based evaluation — a pipeline that continuously draws a sample of production outputs, evaluates them against ground truth or a reference model, and tracks the rate over time. Without this, a hallucination spike can persist for days before it surfaces through user reports.

Containment options include: model rollback to a prior version, prompt rollback to a prior version, reducing the temperature or altering generation parameters to reduce variability, or falling back to a retrieval-only mode that does not involve generation.

### Failure Mode 2: Semantic Drift

Semantic drift is the gradual degradation of output quality over time — not a sudden spike but a slow, cumulative shift away from the intended behavior. It is, in many ways, the most dangerous failure mode because it is the hardest to detect. Each individual output appears acceptable. The degradation only becomes visible when outputs are compared across time windows.

Common causes include: gradual shifts in the distribution of incoming queries, accumulation of retrieval artifacts that subtly skew the context being provided to the model, prompt version changes that look benign but alter model behavior at the margin, and feedback loops where model outputs influence subsequent inputs.

Detection requires trend monitoring over rolling windows — tracking quality metrics not just as point-in-time snapshots but as time series with anomaly detection applied to the trend. A model that scored 0.91 on quality six weeks ago and scores 0.84 today has drifted. Whether that drift is an incident depends on the threshold the team has defined in advance.

### Failure Mode 3: Retrieval Degradation

In systems that use retrieval-augmented generation, the quality of the retrieval pipeline is as critical as the quality of the model. Retrieval degradation occurs when the pipeline begins returning incorrect, irrelevant, stale, or adversarially injected context that the model then incorporates into its outputs.

This is the failure mode illustrated in the opening scenario. It is particularly dangerous because the model's outputs are plausible — the model is doing its job correctly given the context it received. The fault lies upstream, in the data that was retrieved.

Causes include: corruption or schema changes in the underlying data store, embedding model drift that causes semantic mismatches between query embeddings and document embeddings, chunking changes that alter the structure of retrieved passages, and stale document sets that have not been updated to reflect current ground truth.

Detection requires dedicated retrieval quality monitoring: periodic ground-truth queries with known correct retrievals, monitoring retrieval precision and recall over time, and alerting when the distribution of retrieved documents shifts from expected patterns.

### Failure Mode 4: Agentic Overreach

Agentic overreach occurs when an agent takes actions outside its intended operational scope. This is qualitatively different from the other failure modes because it involves real-world consequences that may be irreversible. A model that hallucinates produces incorrect text. An agent that overwrites the wrong database table, sends an unauthorized communication, or initiates an unintended transaction has caused an action-level consequence.

Overreach can stem from: ambiguous tool definitions that leave the agent's scope underspecified, prompt injections that redirect the agent's behavior through malicious input data, edge cases in the decision logic that cause the agent to misclassify situations as within-scope, or accumulated state across multi-turn interactions that shifts the agent's behavioral baseline.

Detection requires behavioral monitoring at the tool call level: tracking which tools are invoked, with what parameters, at what frequency, and comparing that distribution against the expected operational envelope. Anomalies in tool call patterns — unexpected tool invocations, parameters outside the observed distribution, unusual call sequences — are the primary signal.

Containment requires the ability to isolate or halt an agent without taking down the services it depends on. This means designing agent architectures with explicit kill switches, rate limits on irreversible tool calls, and human-in-the-loop checkpoints for high-consequence actions.

### Failure Mode 5: Model-Level Compromise

Model-level compromise is the highest-severity failure mode. It occurs when an attacker successfully manipulates the model's behavior through prompt injection, adversarial inputs, or data poisoning in the retrieval layer. The model is not malfunctioning — it is functioning as the attacker intended.

Prompt injection attacks exploit the model's tendency to follow instructions embedded in the input context. If an attacker can get malicious instructions into the model's context — through a document in the retrieval set, a user input that is passed unfiltered, or a tool response that contains embedded directives — the model may execute those instructions rather than the legitimate system prompt.

Detection requires monitoring for behavioral anomalies that correlate with specific input patterns: sudden changes in output structure, unexpected tool invocations following particular query types, outputs that contain content inconsistent with the system's intended function.

Prevention requires input sanitization, output filtering, and prompt architecture that isolates system instructions from user-controllable content. Response is the same as Failure Mode 4 at the containment level, with additional forensic requirements to understand how the injection occurred and what data or actions were compromised.

---

## Detection Strategies for Each Failure Mode

Knowing the five failure modes is necessary but not sufficient. The practical question is what signals to instrument, what thresholds to set, and how to ensure alerts fire before users are affected at scale.

![0003](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ai-incident-response/0003.png)

The detection architecture for AI systems operates across three layers, each targeting different failure modes:

**Layer 1 — Infrastructure Signals.** These are the metrics traditional APM tools already capture: latency percentiles, token consumption rates, error rates, and cost per request. Infrastructure signals will not catch semantic failures, but they are still necessary — they catch operational failures and provide the baseline against which anomalies in higher layers can be contextualized. A latency spike concurrent with a semantic drift signal means something different than semantic drift in isolation.

**Layer 2 — Semantic Quality Signals.** This is the layer most teams are missing. Semantic quality monitoring requires sampling production outputs and evaluating them against quality criteria — either through comparison to a reference model, through ground truth datasets, or through automated evaluation rubrics. The critical design decision is the sampling rate: high enough to catch spikes within an acceptable detection window, low enough to be operationally sustainable. For most production systems, sampling 3 to 5 percent of outputs through an automated evaluator provides an acceptable balance.

Key metrics at this layer include: quality score distribution over time, hallucination rate (for systems with verifiable facts), retrieval precision for RAG pipelines, and output consistency score (measuring how much the model's responses vary for semantically equivalent inputs).

**Layer 3 — Behavioral Signals.** For agentic systems, behavioral signals are the primary detection mechanism for overreach and compromise. These are signals about what the system is doing, not just what it is outputting: tool call frequency, tool call parameter distributions, action scope relative to the configured operational envelope, and inter-agent communication patterns.

Anomaly detection at Layer 3 requires establishing a behavioral baseline during a stable operating period, then monitoring for deviations from that baseline. Statistical process control methods work well here — tracking control limits around behavioral metrics and alerting when observations fall outside those limits.

The discipline of connecting these three layers into a unified observability pipeline is what separates teams that catch failures before users do from teams that learn about failures from support queues.

---

## The AI Incident Severity Classification Matrix

Not every AI incident is a crisis. Not every quality degradation requires a midnight page. Building an effective response protocol requires a severity classification system that maps failure type and blast radius to a specific response protocol — so the on-call team knows, without deliberation, what to do when an alert fires.

![0004](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ai-incident-response/0004.png)

The matrix I have developed and refined through direct experience classifies incidents across two axes: impact type (what is happening) and impact scope (how many users or systems are affected). The intersection determines severity and response protocol.

**Severity 1 — Agentic overreach with real-world consequences.**
Definition: An agent has taken actions outside its intended scope that have caused or are causing irreversible real-world effects — financial transactions, data modification, unauthorized communications, or actions with legal or safety implications.

Response protocol: Immediate agent halt. Manual review of all actions taken in the preceding window. Incident commander paged. Engineering leadership notified. Legal and compliance notified if data or financial exposure is confirmed. User communication drafted within 30 minutes.

This is the only severity level where the correct first action is always halt, regardless of the ongoing business impact of taking the system offline. An agent that is causing harm must stop before anything else happens.

**Severity 2 — Widespread hallucination or model-level compromise affecting user decisions.**
Definition: The system is producing incorrect outputs at a rate and scale where users are likely to have acted on those outputs. Model-level compromise where attacker influence is confirmed.

Response protocol: System degradation to fallback mode if available (non-AI path, retrieval-only mode, or human review queue). Incident commander paged. Root cause investigation initiated immediately. User communication within 60 minutes. Post-incident analysis scheduled within 24 hours.

**Severity 3 — Retrieval degradation or semantic drift detected proactively.**
Definition: Monitoring has detected quality degradation before users have been significantly affected. The system is still operating, but quality metrics have crossed alert thresholds.

Response protocol: On-call engineer investigates. Incident commander notified but not necessarily paged. Root cause identified and remediation plan developed within 4 hours. If remediation cannot be completed within 4 hours, escalate to Severity 2 protocol.

This is the severity level that proactive monitoring is designed to catch. Catching incidents at Severity 3 before they escalate to Severity 2 is the operational goal.

**Severity 4 — Localized quality degradation within acceptable thresholds.**
Definition: Quality metrics show degradation that is statistically significant but within the acceptable operating range defined by the team. No user impact is confirmed or expected.

Response protocol: Logged and tracked. Investigated during business hours. No immediate escalation. If the trend continues, consider escalation to Severity 3 on the next review cycle.

The classification matrix only works if the thresholds that define each level are established and agreed upon before an incident occurs. Threshold-setting during an incident is one of the most common failure patterns in AI operations — the team is under pressure, there is no agreed reference point, and the severity classification becomes a negotiation rather than a protocol.

---

## The Rollback Problem: Why Model Rollback Is Not a Single Operation

One of the most dangerous assumptions in AI incident response is that rollback is straightforward. In traditional systems, reverting to a previous deployment is well-understood: deploy the prior artifact, verify the service is running, close the incident.

In AI systems, "the prior state" is not a single artifact. It is the intersection of at least four independently versioned components: the model version, the prompt version, the retrieval index version, and the application code version. Rolling back one without coordinating the others can make the incident worse.

Consider a concrete example. A team updates their system prompt (prompt version N+1) and simultaneously updates their retrieval index to a new document corpus (index version N+1). Quality degrades. They roll back the prompt to version N. But the rolled-back prompt was written to work with index version N — it makes assumptions about the structure and content of retrieved documents that no longer hold. The rollback makes the problem worse because it creates a version mismatch that neither version was designed to handle.

The correct mental model for AI rollback is version matrix management: maintaining a record of which combinations of component versions have been validated together, and rolling back to the nearest validated combination rather than rolling back individual components independently.

This requires operational discipline that most teams have not yet implemented: formal version tagging for prompts, model identifiers logged with every inference call, retrieval index versions tied to specific deployment events, and a validation matrix that records which combinations have been tested.

The rollback playbook should specify, for each severity level, the rollback sequence and the validation steps required before confirming that the rollback has resolved the incident.

---

## The Containment Playbook: Isolating Without Cascading

For agentic systems with multiple interconnected components, containment is more complex than simply taking a service offline. An agent that is halted may leave partially completed workflows in an inconsistent state. Tool calls that were in-flight may complete or fail in unpredictable ways. Downstream systems that were receiving the agent's outputs may need to be isolated as well.

Effective containment for AI systems requires four design-time decisions that cannot be made during an incident:

**Circuit breakers at the agent boundary.** Every agent should have a mechanism to halt its own execution — a circuit breaker that can be triggered by a monitoring signal, a human operator, or an automated safety check. This circuit breaker should be testable and should be tested regularly, not just documented.

**Idempotent tool calls wherever possible.** If an agent's tool calls are idempotent, a partial execution can be safely retried or reversed. If they are not, partial executions may leave state in a condition that is neither the pre-incident state nor the intended post-execution state. Design tool interfaces for idempotency as a first-class requirement.

**Compensation transactions for irreversible operations.** For operations that cannot be made idempotent — database writes, financial transactions, external API calls that trigger downstream actions — design compensating transactions that can be invoked during containment to reverse or neutralize the action. These compensation paths should be implemented and tested before they are needed.

**Dependency mapping.** Know, before an incident, which systems depend on the AI component's outputs. When containment requires isolating the AI component, the dependency map tells you which downstream systems need to be notified, which can continue operating with degraded or cached data, and which must also be halted.

---

## Post-Incident Analysis: Reconstructing What Happened in a Probabilistic System

Traditional post-incident analysis follows a traceable causal chain: this code change, deployed at this time, caused this function to behave in this way, producing this error. The causal chain is deterministic and, with sufficient logging, fully reconstructable.

For AI systems, post-incident analysis is more forensic than retrospective. The system's behavior was probabilistic. The same inputs on the same model on the same day might have produced different outputs. Reconstructing what happened requires a different toolkit.

The core elements of an AI post-incident analysis are:

**Prompt lineage reconstruction.** Which prompt version was active during the incident? What changes were made to that prompt in the preceding two weeks? Were any parameters changed — temperature, max tokens, few-shot examples — that could account for the behavioral shift?

**Model version audit.** What model version was serving traffic during the incident? Were there any model updates from the provider in the preceding window? Some providers update model weights without version identifier changes — this is a known blind spot that requires mitigating through regular behavioral benchmarks, not just version tracking.

**Retrieval context sampling.** For RAG systems, retrieve a sample of the contexts that were being served to the model during the incident window. Does the quality of those contexts explain the quality of the outputs? Is there a specific document, document type, or query pattern that correlates with the failures?

**Behavioral trace analysis.** For agentic systems, review the action traces from the incident window. Which tools were called, in what sequence, with what parameters? Is there a pattern in the invocations that precede the failure? Was there a specific input pattern that triggered the anomalous behavior?

**User impact quantification.** How many users received outputs that were affected by the incident? What actions did those users take based on those outputs? This is not just a reporting question — it is necessary for determining whether further remediation is required and for calibrating the severity of similar future incidents.

---

## Five Documents Every Team Should Have Before the Next Incident

The most important insight from analyzing AI incidents across the industry is that the teams that respond effectively are not the teams that are smarter or faster under pressure. They are the teams that made decisions before the incident, when they had time to think clearly. Those decisions are encoded in documents that exist before anything goes wrong.

![0005](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ai-incident-response/0005.png)

Here are the five documents that belong in every AI team's incident preparation kit:

**Document 1: The AI Failure Mode Registry.**
A structured record of each AI failure mode relevant to your specific system, including the detection signal for each mode, the containment options, the rollback sequence, and the communication template. This is not a generic document — it must be specific to your system's architecture, your team's tool set, and your organization's communication protocols.

**Document 2: The Version Matrix.**
A record of every validated combination of model version, prompt version, retrieval index version, and application code version. Updated at every deployment. Referenced at every rollback. This is the document that prevents the version mismatch problem described earlier.

**Document 3: The Threshold Reference.**
A documented record of the quality thresholds that define Severity 3, Severity 2, and Severity 1 for your system — the specific metric values, the time windows over which they are measured, and the reasoning behind each threshold. Agreed upon by engineering leadership before any incident, not during one.

**Document 4: The Dependency Map.**
A current map of every system that depends on your AI component's outputs, including the expected input format, the downstream effect of degraded or incorrect outputs, and the contact for the owning team. Updated at every architecture change.

**Document 5: The Communication Templates.**
Pre-written communication templates for each severity level — for users, for engineering leadership, and for external stakeholders if applicable. The structure should be: what we know, what we are doing, what you should do now, and when you will hear from us next. These templates reduce the cognitive load on the incident commander at the moment when cognitive load is highest.

The discipline of maintaining these five documents is itself a signal of operational maturity. Teams that have them have thought carefully about their AI systems' failure modes. Teams that do not have them are discovering those failure modes for the first time during the incident.

---

## What Most Teams Get Wrong

The most common AI incident response failure is applying traditional incident severity definitions to AI failures.

In traditional systems, Severity 1 means the service is down — observable, bounded, recoverable. The incident ends when the service is back up. Users know something went wrong because they could not complete their task.

In AI systems, Severity 1 means the system is producing harmful outputs confidently and at scale. The incident may have been ongoing for days before detection. Users did not know something was wrong — they received responses that looked correct. Some of them acted on those responses. The blast radius of an AI Severity 1 incident extends beyond the incident window because the incorrect outputs already reached users before the incident was detected.

This is not a subtle distinction. It has direct implications for how severity is classified, how communication is timed, and how remediation is scoped. A team that defines Severity 1 as "service is down" will systematically underrespond to AI incidents where the service is up and producing harm.

The second most common failure is building the incident response process for the AI system you think you have, not the AI system you actually have. Teams frequently discover, during their first serious incident, that their system has dependencies they did not document, failure modes they did not anticipate, and rollback sequences that interact in ways they did not design for. The investment in understanding the system deeply enough to build a real playbook is the investment that prevents this discovery from happening at the worst possible moment.

---

## Where This Is Heading

The discipline of AI incident response is maturing rapidly, driven by necessity. As AI systems handle more consequential decisions — financial recommendations, medical information, legal document processing, infrastructure automation — the cost of incidents grows proportionally, and the regulatory scrutiny of how those incidents are handled is increasing.

The direction this field is moving is toward formalized AI operations as a distinct engineering discipline, with its own tooling, its own runbooks, its own on-call rotations, and its own post-incident analysis processes that are as rigorous as the software incident processes that developed over the last two decades.

Several developments are accelerating this:

Automated behavioral monitoring is becoming more sophisticated, with tools that can detect semantic drift and hallucination spikes without requiring manual evaluation. The sampling-based evaluation pipelines that once required significant custom engineering are becoming standardized components.

Regulatory frameworks in multiple jurisdictions are beginning to require documented incident response procedures for AI systems that handle personal data or make consequential decisions. The teams building these procedures now will not be building them under regulatory pressure later.

The concept of AI system health as a distinct operational concept — separate from infrastructure health — is gaining traction in the engineering community. The monitoring dashboards of the next generation of AI operations will show semantic quality scores, behavioral anomaly indices, and retrieval health metrics alongside the latency and error rate charts that exist today.

The teams that are building these capabilities now are establishing practices that will compound. Every incident they handle with a proper playbook produces artifacts — refined thresholds, updated failure mode registries, improved communication templates — that make the next incident cheaper and faster to resolve. The teams that are not building these capabilities are accumulating operational debt that will be collected at the worst possible time.

---

## Building the Playbook Starts Now

![0006](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/ai-incident-response/0006.png)

An AI system without an incident response playbook is not a production system. It is a system waiting for its first serious incident to discover what its failure modes actually are.

The frameworks in this post are not theoretical constructs. They are the operational backbone that separates teams that manage AI reliability proactively from teams that manage it reactively.

Start with the five documents. Then build the detection pipelines. Then run a tabletop exercise that walks through each severity level using realistic scenarios. Do that work now, when the system is running and the team has time to think. The alternative is doing it in the middle of the incident, under pressure, with incomplete information.

The engineering discipline of AI incident response is not a specialization for large organizations or research teams. It is the baseline operational requirement for any team running AI in production.

---
