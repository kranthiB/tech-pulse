---
id: gen-ai/unattended-agents
title: "Unattended Agents: Engineering for the Hours Nobody Is Watching"
sidebar_label: Unattended Agents
previous_page: gen-ai/ai-native-engineering-culture
next_page: gen-ai/ai-driven-software-development
---

<div style="text-align: right;">
    <a href="https://kranthib.github.io/tech-pulse/" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Back to Home →</a>
</div>

---

![0000](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/unattened-agents/0000.png)

# Unattended Agents: Engineering for the Hours Nobody Is Watching

**Every agent your team has ever reviewed was reviewed while a person was watching it. That is the quiet flaw in most agent evaluations. The person who tests an agent is also the person who stops it, corrects it, limits it, and notices when something feels wrong. Remove that person, run the agent on a schedule or an event, and you have not deployed the agent you tested. You have deployed a different system that happens to share its code.**

![0001](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/unattened-agents/0001.png)

---

## The Night Shift Nobody Staffed

Consider a pattern that is becoming common. A finance operations team builds an agent to reconcile vendor invoices against purchase orders. In the pilot, an analyst starts the agent each morning, watches it work through a batch, reads its proposed adjustments, and approves them. The pilot is a success. Accuracy is high, the analyst saves hours, and the sponsor asks the obvious question: why are we starting this by hand? So the team wires it to a queue. When a batch file lands overnight, the agent wakes up, reconciles, and posts adjustment entries directly. The scenario here is a composite of failure patterns, simplified for clarity.

Three weeks later, the total in the ledger does not match the total in the source system. Nobody can say when it started. The investigation finds two independent causes. First, the queue redelivered a batch message after a slow model call exceeded the acknowledgement window, so the same batch was processed twice, and the agent, which was permitted to create adjustment entries, created them twice. Second, the agent kept a working notes file between runs so it could remember vendor quirks. On one night it read a malformed vendor comment, wrote a rule about it into the notes, and applied that rule to every later run for that vendor.

No individual step was wrong in a way any test would have caught. The model behaved as designed. The queue behaved as designed. The notes file did what it was built to do. The failure lived in the space between the components, in the exact place where a watching analyst used to sit.

That is the subject of this post. Unattended operation is not a scheduling detail added to an agent after it works. It is a different class of system with its own failure modes, its own controls, and its own readiness bar. The engineering leaders who treat it that way will extend autonomy safely. The ones who treat it as a cron entry will find out what their agents were doing while nobody looked.

---

## Why Unattended Is a Different Class of System

When a person sits in front of an agent, they provide five services so consistently that nobody thinks to list them.

**Live correction.** The person can stop the agent mid-run the moment it heads in the wrong direction. An unattended run has no such moment. It completes, or it fails, and either way the damage or the value is already in the world.

**Implicit scoping.** The person asks for what they mean and does not ask for what they do not. They would never say "reconcile everything and also delete the old records," so the agent never receives that instruction. In an unattended run, scope comes from configuration and from whatever data arrives, and data can say anything.

**A natural rate limit.** A person reads, thinks, and clicks. That pace caps how much an agent can do per hour. An unattended agent runs at machine speed, limited only by its permissions and its infrastructure.

**Immediate anomaly detection.** People notice when output feels off, often before they can explain why. Unattended runs replace that instinct with whatever monitoring was built, and monitoring only catches what someone predicted.

**Accountable presence.** When a person runs the agent, a name is attached to the action. When a trigger runs it, the accountability has to be assigned on purpose, or it does not exist.

Each of these is a control that was never designed. It simply came with the human. The engineering task for unattended agents is to turn every one of them into a designed mechanism: a stop control that works without a person, scope enforced outside the model, ceilings on speed and volume, monitoring that expects specific failure shapes, and a named owner.

This is also why a successful pilot is weak evidence. The pilot measured the agent plus the human. The production system is the agent alone. The gap between those two measurements is exactly the set of controls the human was providing.

**Most Teams Get This Wrong:** They test the agent thoroughly and the surrounding system barely at all. In unattended operation, the surrounding system is the product. The agent is one component inside it.

---

## The Trigger Surface: Four Ways an Agent Wakes Up

An interactive agent has one way to start: a person asks. An unattended agent has a trigger, and the trigger is part of its authority. Whoever or whatever can fire the trigger can cause the agent to act, using the agent's full permissions. That makes every trigger both a reliability surface and a security surface. There are four kinds worth designing for separately.

**The clock.** Scheduled runs are the simplest trigger and the source of the most boring failures. Runs overlap when one takes longer than the interval. Runs are missed when infrastructure restarts. Many agents fire at the top of the hour and hammer a shared system at once. The controls are standard but often skipped: a single-flight lock so a new run refuses to start while a previous one holds the lease, an explicit policy for missed runs (skip, catch up once, or catch up all), and jitter so a fleet of agents does not stampede.

**The event.** A data change, a file landing, a queue message. Event triggers are attractive because they eliminate polling, but they arrive with delivery semantics that most agent teams have never had to think about. Nearly every reliable queue guarantees at-least-once delivery, which means duplicates are a normal condition, not an error. Events also arrive in bursts, out of order, and occasionally as storms when an upstream system misbehaves. The controls are deduplication by stable event identity, ordering assumptions stated explicitly, and a backpressure policy that decides what the agent does when a hundred events arrive in a minute.

**The external call.** A webhook or API endpoint that starts a run. This is the widest trigger surface. Anyone who can reach the endpoint can make the agent act, and the payload that arrives is untrusted input that the agent will read. Two controls are non-negotiable. The endpoint must authenticate the caller, not merely obscure its address. And the payload must be treated as data, never as instruction: the agent's task definition comes from configuration the owner controls, while the payload only fills in the fields the task expects. A payload that can rewrite the task is a remote control for your agent.

**The chain.** One agent's output triggers another. Chained triggers create amplification and loops. A single event can fan out into dozens of downstream runs, and two agents can wake each other indefinitely if each one's write is the other's trigger. The controls are a run lineage identifier carried through every hop, a maximum chain depth, and loop detection that halts when the same lineage revisits the same agent.

A useful rule ties these together. **The reach of the trigger defines the attack surface of the agent.** If the trigger is a private schedule, the surface is small. If it is a public endpoint, the agent is exposed to anyone who can send a request. Design the trigger first, and set the agent's permissions to match the least trusted party who can fire it.

![0002](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/unattened-agents/0002.png)

**Most Teams Get This Wrong:** They secure the agent's tools and forget the trigger. A tightly scoped agent behind an unauthenticated endpoint is not tightly scoped. It is tightly scoped for whoever finds the endpoint first.

---

## Idempotency and the Duplicate-Event Problem

Return to the reconciliation agent. The duplicate adjustments were not caused by a bug in the agent. They were caused by a fact of distributed systems that applies to every unattended agent: **a run can be executed more than once even when nothing failed.** Queues redeliver. Schedulers retry. Infrastructure restarts a worker that looked unhealthy. Any of these will re-run work that already partly or fully completed.

Traditional services handle this with idempotency: performing an operation twice has the same effect as performing it once. Agents make idempotency harder for a specific reason. The usual technique is to derive an idempotency key from the request content. But an agent's generated content is not deterministic. The same input can produce a differently worded adjustment note on the second attempt, so a key built from the output will not match, and the duplicate slips through.

The answer is to change where the key comes from and where the non-determinism lives.

**Key from the event, not the output.** The idempotency key for every effectful step is built from the identity of the triggering event and the step within the run, for example the event identifier plus the sequence number of the action. It never includes generated text. Two attempts at the same step produce the same key regardless of how the model phrased its answer.

**Separate planning from applying.** Let the agent do what it is good at: read the situation and produce a plan. The plan is a structured artifact, a list of intended actions each carrying its key. A deterministic executor, ordinary code with no model in it, applies the plan. The executor checks a ledger before each action, applies the action if the key is new, and records it. All the non-determinism stays in the planning step. All the side effects happen in a step that is fully deterministic and safe to repeat.

**Commit the effect and the record together.** The ledger entry and the effect must succeed or fail as one unit. If the record is written after the effect, a crash in between leaves an effect with no record, and the retry repeats it. If the record is written before the effect, a crash leaves a record with no effect, and the retry skips work that never happened. Use a single transaction where the system allows it. Where it does not, use a ledger with explicit states, planned, applied, confirmed, and a reconciliation step on restart that resolves anything left in the middle.

**Decide the dedupe window on purpose.** A ledger that remembers forever grows without bound. A ledger that forgets too soon lets a late redelivery through. The window should exceed the longest plausible redelivery delay, and that number should be written down and monitored, not assumed.

There is a side benefit that teams tend to discover afterward. The plan artifact is also the best audit record an agent run can produce. It states what the agent intended, separately from what the executor did. When the two diverge, the divergence is a finding.

![0003](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/unattened-agents/0003.png)

**Most Teams Get This Wrong:** They treat retries as an infrastructure concern that lives below the agent. For an agent with side effects, retry behavior is part of the agent's correctness. If the agent's actions are not safe to repeat, the platform's retry policy is a source of incidents.

---
## State That Compounds Across Runs

Many unattended agents keep something between runs: a notes file, a working directory, a cache of prior decisions, a list of vendor quirks. Teams add this for good reasons. Without it, the agent rediscovers the same facts every night, wastes time, and repeats the same mistakes. But persistent state changes the risk profile of an unattended agent more than almost any other design choice, because **in an unattended system, an error does not stay in the run that produced it.**

In an interactive session, a wrong inference is visible. The person reads it, disagrees, and moves on. In an unattended agent, a wrong inference written to durable state in one run becomes an input to every later run, and nobody reads it in between. The reconciliation agent's malformed-comment rule is the archetype. Three distinct problems follow.

**Drift.** Small, individually reasonable updates accumulate into behavior nobody chose. After two hundred runs, the state file encodes a set of habits that no human ever reviewed. The agent is now partly a product of its own history.

**Persistence of untrusted input.** Anything the agent reads from outside can end up in its state. If the agent summarizes a document into its notes, and the document contained an instruction, the instruction is now stored in a place the agent treats as its own knowledge. The attacker no longer needs to be present at run time. They planted the instruction once and it fires on every run afterward. This is one of the most durable forms of manipulation available against an unattended system, precisely because the original payload can be deleted and the effect remains.

**Unreproducibility.** When run number eighty-seven does something odd, you need to recreate the conditions. If the agent's behavior depended on a state file that has since been overwritten, you cannot. The failure is real and the evidence is gone.

The controls follow from separating two kinds of state that teams usually blend together.

**Working state** lives for one run and is discarded at the end. The agent may write whatever it needs while it works. Nothing carries forward, so nothing compounds.

**Durable state** carries across runs and is treated as configuration, not as scratch space. It has a defined schema rather than free-form prose the agent rewrites. It has a version. Changes to it are proposals: the agent submits a suggested change, and either a deterministic validation or a human approves it before it becomes something the next run reads as fact. Entries carry an origin and an expiry, so old and unverified knowledge ages out instead of hardening.

Finally, every run should write a manifest: the trigger and event identity, the version of the durable state it read, the model and configuration versions in use, the plan it produced, and the effects that were applied. The manifest is what makes run eighty-seven reproducible. It costs little to write and is the first thing anyone will ask for during an incident.

**Most Teams Get This Wrong:** They give the agent a writable memory because it improves results in testing, and never ask who reviews what gets written. Writable state that nobody reads is an unreviewed configuration change happening every night.

---

## The Side-Effect Ladder: Observe, Draft, Write, Act

Not all agent actions carry the same risk, and unattended operation is where that difference matters most. A person is not available to catch a bad action before it lands, so the design question becomes: for each thing this agent can do, what is the cost of it being wrong, and can that cost be undone? A four-rung ladder makes the answer explicit.

**Rung one: Observe.** The agent reads and reports. It changes nothing. A wrong answer produces a bad report, which is a real cost but a bounded one. Most unattended agents should begin here, and many valuable ones can stay here permanently.

**Rung two: Draft.** The agent produces an artifact that a person or a downstream process reviews before anything happens: a proposed ticket, a drafted message, a suggested adjustment. Nothing takes effect until the review, so a wrong draft costs review time, not damage.

**Rung three: Write, reversibly.** The agent makes changes that can be undone automatically within a defined window: creating a record, applying a label, staging a change, opening a pull request. The critical requirement is that the undo path exists and has been tested. An action is only reversible if someone has actually reversed it in a rehearsal.

**Rung four: Act, irreversibly or externally.** The agent does something that cannot be taken back or that leaves the organization: sending a message to a customer, moving money, deleting data, publishing, deploying. A wrong action here is a real-world event.

Four rules turn the ladder from a diagram into a control.

Promote per action type, not per agent. An agent might be trusted at rung three for creating tickets and held at rung two for closing them. The unit of trust is the specific action against the specific resource, and it should be recorded that way.

Start low and climb on evidence. Every action type enters at the lowest rung that still delivers value, and moves up only after a track record at the rung below, measured over enough runs to include the unusual ones.

Rung four needs a release mechanism that does not depend on presence. The person is not there, so approval becomes asynchronous: the agent places the action in an approval queue and stops. The queue design carries the whole safety property. Each queued item carries the context needed to decide quickly. Each has an expiry. And the default on expiry is that nothing happens. An approval queue that quietly executes after a timeout is not a control. It is a delay.

Where an action must be fully automatic at rung four, the substitute for a human is hard limits enforced outside the model: value caps, allow-lists of recipients or targets, and rate ceilings, applied by the executor regardless of what the agent planned.

![0004](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/unattened-agents/0004.png)

**Most Teams Get This Wrong:** They grant an agent one permission set for everything, sized for its riskiest action. The safe actions inherit the danger of the dangerous ones, and the review effort is spread evenly instead of concentrated where it matters.

---

## Budgets, Blast Radius, and the Kill Switch

Unattended agents fail in a way interactive agents rarely do: they keep failing at full speed, for hours, with nobody to interrupt them. The controls for that are ceilings that stop the damage from growing and a stop mechanism that works fast. Three ceilings cover most of the ground.

**A spend ceiling.** Model calls, tool calls, and compute cost money, and an agent stuck in a retry loop can spend a month of budget in a night. Set a limit per run and a limit per day. A run that reaches its limit halts and raises an alert. It does not degrade quietly, and it does not decide for itself that the task is important enough to continue.

**An action ceiling.** A cap on the number of effectful actions per run and per hour. Legitimate workloads have a natural volume. An agent that suddenly wants to make ten times the usual number of changes is not being productive. It is malfunctioning, or it is being steered. The ceiling converts that anomaly into a halt.

**A scope ceiling.** A cap on how much of the world one run may touch: the number of records, the total value affected, the number of distinct targets. Scope ceilings define the blast radius in a form a business owner can read. "This agent can never modify more than a fixed number of accounts in one run" is a sentence a risk committee can approve.

All three share a rule that matters more than any number: **they are enforced outside the agent.** A ceiling written into the prompt is a suggestion to a system that reasons about suggestions. A ceiling enforced by the executor, the gateway, or the credential itself is a fact about the environment. The agent cannot talk its way past it, and neither can text it read from a malicious document.

Three failure patterns explain why ceilings matter. The retry storm, where an error triggers a retry that triggers the same error. The re-trigger loop, where the agent's own output fires its own trigger. And the slow burn, where a small, steady overspend or over-action never trips a per-run limit but exhausts the daily one. Per-day and per-hour ceilings exist for the slow burn.

The other half of containment is the ability to stop. A kill switch is not a single button. It is four levels, and the right one depends on what is happening.

**Pause the trigger.** Stop new runs from starting. Nothing in flight is affected. This is the gentlest option and the first one to reach for.

**Drain or cancel.** Decide what happens to runs already in progress: let them finish, or cancel them at the next safe point.

**Revoke.** Invalidate the credentials the agent runs with. This is the option that works even when everything else is misbehaving, because it does not depend on the agent, the scheduler, or the trigger cooperating.

**Quarantine.** Preserve the state, the manifests, and the ledger exactly as they were so that the investigation has evidence. Teams that skip this level often fix the problem and lose the explanation.

Two practices separate a real kill switch from a comforting one. It must be operable by whoever is on call, without waiting for a code change or a deployment. And it must be drilled. The measure that matters is the time from the decision to stop until the agent has actually stopped, and that number only becomes known, and improves, when the team rehearses it.

![0005](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/unattened-agents/0005.png)

**Most Teams Get This Wrong:** They build the kill switch and never use it. The first time it is exercised is during an incident, when the person on call discovers it needs a credential they do not have or a service that is itself down.

---

## Ownership: Every Unattended Agent Needs a Named Human

An interactive agent has an obvious accountable person: whoever is using it. An unattended agent has nobody by default, and that vacancy is a risk in itself. The most common long-term failure of unattended agents is not a dramatic incident. It is the orphan: an agent that keeps running long after the person who built it has moved teams, changed roles, or left, still holding credentials, still acting, with no one who understands what it is for.

Every unattended agent needs a small set of facts recorded somewhere a person can find them.

A named owner, and a backup. Someone whose job includes the answer to "why did this happen." A purpose statement, a sentence or two on what the agent is for and what it must never do. Its declared authority, meaning the ladder rung for each action type it is permitted. An alert route, meaning where its warnings go and who is expected to respond, which must be a person or a rotation, never an unmonitored mailbox. A review date, when someone will look at whether it is still needed and still safe. And retirement criteria, the conditions under which it gets turned off.

This does not require a platform. A registry that starts as a shared table with one row per agent is enough to change behavior, because it forces the questions to be asked and makes the answers visible. What matters is that the registry is the gate: an agent without a row does not get credentials.

Ownership also has to include monitoring for silence. Teams instrument the failures they can imagine, such as errors, alerts, and ceiling breaches, and forget the failure that produces no signal at all: the agent that simply stops. A nightly agent that did not run last night looks, to most monitoring, exactly like a nightly agent that had nothing to do. The fix is an expectation of life. Each agent declares when it should run and roughly what it should produce, and a missing heartbeat or an unexpectedly empty result raises an alert to the owner.

**Most Teams Get This Wrong:** They route alerts to a shared channel that everyone can see and nobody owns. An alert that reaches everyone reaches no one. Assign it to a named person or an on-call rotation with authority to act.

---
## A Worked Example: Taking the Reconciliation Agent From Pilot to Production

Return once more to the invoice reconciliation agent, this time redesigned so that it can run overnight with nobody watching. The goal is not to make the agent smarter. It is to replace, one by one, the services the analyst used to provide.

**The trigger.** The queue consumer authenticates its source and accepts only messages from the expected upstream system. It takes a lease before starting, so a redelivered message cannot start a second concurrent run. The batch payload supplies the file location and batch identity and nothing else. The task the agent performs is fixed in configuration the owner controls.

**The plan.** The agent reads the batch and produces a structured plan: a list of proposed adjustments, each carrying a key built from the batch identity and its position in the batch. The agent posts nothing. Its output is a document.

**The executor.** Ordinary code reads the plan and applies it. Before each adjustment it checks the ledger for the key. If the key exists, it skips. If not, it applies the adjustment and records it in the same transaction. When the queue redelivers the batch, every key is already present, and the second pass does nothing.

**The ladder.** Creating an adjustment is a rung-three action: the entry is staged and can be reversed automatically during a review window before it posts to the general ledger. Adjustments above a value threshold are rung four in effect, so they go to an approval queue with an expiry, and if nobody approves before it lapses, the adjustment is dropped and reported.

**The ceilings.** The executor enforces a maximum number of adjustments per run, a maximum total value per run, and a daily spend limit on model calls. A run that hits any of them halts and pages the owner. None of these numbers appears in the prompt.

**The state.** The agent starts each run with no memory of previous runs. Vendor quirks live in a versioned reference file. When the agent thinks it has found a new quirk, it proposes an entry, which lands in a review queue and is never read as fact until a person approves it. The malformed vendor comment from the original incident would have become a proposal that someone rejected.

**The signals.** Every run writes a manifest. The agent is expected to run each night and to process a plausible number of items. A missing run or an empty result alerts the owner. The kill switch is documented, and the on-call engineer has drilled it.

**The owner.** The agent has a row in the registry with a named owner, a backup, an alert route to a rotation, and a review date.

The point of the redesign is what it did not require. It did not require a better model. The same model, the same prompts, and the same reconciliation logic sit inside a system where a duplicate delivery is harmless, a bad inference cannot become durable fact without review, and a runaway loop halts itself. The pilot proved that the agent could reconcile. The redesign proves that the system around it can be trusted to run at night.

---

## What Most Teams Get Wrong

**Treating pilot success as production evidence.** The pilot had a watching human, which means it tested the wrong system. Ask a sharper question: which of the five services the human provided is still present in production, and which have been replaced by a tested mechanism? The answer is usually that most have simply vanished.

**Enforcing limits through the prompt.** "Never process more than fifty items" written into instructions is a request. Ceilings, allow-lists, and approval requirements belong in code and credentials that the agent cannot rewrite or reason around.

**Sharing credentials between the interactive and unattended versions.** The interactive assistant that a person supervises and the same agent running unattended should not hold the same permissions. The supervised version can afford broad access because a person is watching. The unattended version should hold the narrowest credentials that support its declared rung, and they should be distinct so revoking one does not break the other.

**Measuring the average and ignoring the tail.** Unattended agents are judged by how they behave on their worst night, not their typical one. A run that is correct ninety-nine times and duplicates a payment on the hundredth has not achieved ninety-nine percent success. It has achieved one incident. Evaluate against duplicates, bursts, malformed inputs, and partial failures, not just typical batches.

**Having no plan for the end.** Agents accumulate. Each one was justified when it was built, and none of them come with a date for review. A registry with a retirement condition for every agent is the cheapest defense against the slow buildup of unattended software nobody remembers approving.

---

## The Unattended Readiness Framework

The controls in this post reduce to eight gates. An agent is ready to run without a person when it can show, not assert, that each gate is in place. Score each gate zero if it is absent, one if it is partial or untested, and two if it is in place and has been exercised.

**Gate 1, Trigger.** The trigger is authenticated, single-flight, and rate-limited, and the payload is treated as data. The agent's permissions are sized for the least trusted party who can fire it.

**Gate 2, Idempotency.** Every effectful step carries a key built from event identity, not generated content. Effects and ledger entries commit together. A duplicate delivery has been tested and is harmless.

**Gate 3, Authority.** Every action type is mapped to a rung of the side-effect ladder. Rung-three actions have a tested undo path. Rung-four actions sit behind an approval queue that defaults to no action, or behind hard limits enforced outside the model.

**Gate 4, State.** Runs are stateless by default. Durable state has a schema, a version, an origin, and an expiry, and changes to it are reviewed before they take effect.

**Gate 5, Ceilings.** Spend, action count, and scope are capped per run and per day, enforced outside the agent, and a breach halts the run and alerts a person.

**Gate 6, Stop.** The kill switch has four levels, works for the on-call engineer without a deployment, and has been drilled with a measured time to stopped.

**Gate 7, Signal.** Every run writes a manifest. Failures, ceiling breaches, and silence all raise alerts. An expected run that does not happen is treated as an event.

**Gate 8, Owner.** A named owner and backup, an alert route to a person or rotation, a declared authority, a review date, and retirement criteria are recorded in the registry, and the registry gates the credentials.

The scoring gives a maximum of sixteen. As a working guide, an agent scoring below ten should not run unattended with any write access. An agent between ten and thirteen is a candidate for the first three rungs of the ladder only. An agent at fourteen or above has earned consideration for rung-four actions, still subject to the approval or hard-limit requirement in Gate 3.

The scoring is intentionally blunt. Its purpose is to make the conversation concrete. A team that scores itself honestly usually finds that the low-scoring gates are the same few every time: idempotency, the stop mechanism, and ownership. Those are also the gates that produce the incidents.

![0006](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/unattened-agents/0006.png)

---

## Where This Is Heading

Unattended operation is where agents stop being tools that people use and become workers that organizations employ. That shift changes what platforms will offer. Triggers, leases, ledgers, and approval queues will move from things each team builds by hand to first-class primitives, in the same way that retries and health checks moved into service infrastructure over time.

The control surface will keep moving outward from the model. Prompts will remain the place where the task is described, and policy engines, executors, and credentials will become the place where limits live. That separation, non-deterministic reasoning inside a deterministic envelope, is likely to become the standard shape of any agent given authority to act.

Authority for unattended agents will also be earned the way it is earned by people: incrementally, on evidence, with a record. Expect the questions asked of these systems to change from "does it work" to "show me its manifest, its ledger, and its owner." Organizations that already produce those artifacts will scale their agent programs with confidence. Organizations that do not will find that the first serious incident becomes the moment they are required to build them, under pressure, and without the calm to design them well.

---

## The Decision to Make This Week

List every agent in your organization that can run without a person present. Include the ones on a schedule, the ones triggered by events, the ones behind an endpoint, and the ones started by other agents. For each, answer three questions in writing:

What wakes it? What can it change? Who gets the alert?

If any answer is unknown, or if the answer to the third question is a channel instead of a person, that agent is your first project. Everything else in this post is how you fix it, one gate at a time.

---

