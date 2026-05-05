---
id: gen-ai/a2a-protocol
title: "Agent-to-Agent Protocols: Why MCP Alone Is Not Enough"
sidebar_label: Agent2Agent (A2A) Protocol
previous_page: gen-ai/mcp
next_page: gen-ai/agent-memory
---

<div style="text-align: right;">
    <a href="https://kranthib.github.io/tech-pulse/" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Back to Home →</a>
</div>

![Agent-to-agent protocols, MCP, and orchestration](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/a2a/0000.png)

# Agent-to-Agent Protocols: Why MCP Alone Is Not Enough

**How A2A fills the coordination gap MCP was never meant to solve, and how to compose both in production.**

---

## The Protocol Gap Nobody Talked About

In early 2024, most engineering teams building with AI agents had one protocol conversation: MCP. The Model Context Protocol had solved a genuine pain point: how agents connect to tools. It gave the ecosystem a shared language for capability discovery, tool invocation, and structured data access. For a season, that felt like enough.

It was not enough.

The gap that emerged was not about tools. It was about agents. As teams moved from single-agent demos to multi-agent production systems, they discovered a problem that MCP was never designed to solve: how does one agent hand work to another? How does an agent declare its capabilities so that a calling agent can decide whether to delegate? How does an agent negotiating a task with a peer handle failure, retry, or partial results?

Every team answered these questions differently. Some built bespoke JSON schemas over HTTP. Some used message queues with undocumented envelope formats. Some embedded agent communication inside their orchestration framework in ways that made the logic impossible to extract or reuse. The multi-agent ecosystem fragmented exactly as the single-agent tool ecosystem had before MCP, except faster, because multi-agent adoption was growing faster.

The agent-to-agent protocol problem needed its own solution. That solution exists now. Most engineering teams have not yet absorbed what it means for how they build.

This article walks through the full protocol picture: what A2A is, how it composes with MCP, what the Agent Card primitive changes architecturally, where the N-squared connectivity problem bites teams who skip the orchestration layer, and how to make the implementation decision correctly for your own system.

---

## The Protocol Gap A2A Was Built to Fill

![Protocol gap and pre-A2A fragmentation](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/a2a/0001.png)

Before A2A existed, every multi-agent framework shipped its own inter-agent communication mechanism. LangGraph had its own state handoff model. AutoGen had its own message envelope. Custom frameworks had whatever the original author thought made sense at the time. The result was an ecosystem of agents that could not talk to each other across framework boundaries, even when the underlying task was straightforward.

This was not a niche problem. Consider what a real multi-agent system requires. A research orchestrator needs to delegate a web retrieval subtask to a search agent. A coding agent needs to hand off a failing test to a debugging agent. A customer service orchestrator needs to route a billing dispute to a specialist agent that holds current account data. Each of these handoffs requires the calling agent to know four things:

1. What the receiving agent is capable of
2. What input format the receiving agent expects
3. What the calling agent should expect back
4. What to do when the handoff fails or the result is partial

None of these four questions can be answered reliably without a shared protocol. A bespoke JSON schema answers question two for a specific pair of agents on a specific day, but it provides no mechanism for capability discovery, no standard error taxonomy, and no interoperability across team or vendor boundaries.

The pre-A2A world required engineers to maintain hand-rolled coordination logic for every agent pair. In a system with ten agents, that is potentially ninety coordination relationships. In a system with twenty agents, it is three hundred eighty. The combinatorial math is the problem, and the only structural solution is a protocol that all agents share.

IBM recognized this when building ACP (the Agent Communication Protocol) inside the Linux Foundation's BeeAI project. The ACP design philosophy was REST-native simplicity: no SDK required, multi-modal message envelopes, and explicit capability negotiation. It gained traction among teams that were skeptical of framework-heavy approaches and wanted clean HTTP semantics they could implement in any language.

Meanwhile, a coalition of major AI labs and cloud providers was converging on a similar set of requirements from the enterprise deployment side. The result was A2A (the Agent2Agent Protocol), which entered production at over 150 organizations by April 2026 and is now co-governed under the Linux Foundation with participation from the organizations whose infrastructure runs most of the world's AI workloads.

ACP did not compete with A2A. It merged into A2A, contributing its REST-native design principles and multi-modal messaging model. The resulting protocol inherits the best of both lineages: the simplicity of ACP's HTTP semantics and the enterprise-scale capability model of A2A.

The gap that existed before is now filled. The question for engineering teams is whether they understand the protocol well enough to use it correctly.

---

## MCP vs. A2A: Different Layers, Not Competitors

![MCP vs A2A: vertical tools vs horizontal agents](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/a2a/0002.png)

The most common error I see in teams adopting A2A is framing it as a replacement for MCP. It is not. MCP and A2A solve different layers of the same problem, and confusing the two layers produces architectures that fight themselves.

MCP is a vertical protocol. It handles the relationship between an agent and a tool: a database query executor, a file system reader, a web search API, a code interpreter. The agent is the caller. The tool is the callee. The relationship is asymmetric: the agent has goals, the tool has capabilities, and MCP provides the vocabulary for capability discovery and invocation. The communication pattern is request-response, the trust relationship flows one way, and the tool does not make decisions about whether to accept the request.

A2A is a horizontal protocol. It handles the relationship between two agents. Both parties are active reasoners. Both can decline, negotiate, request clarification, or propose alternatives. The relationship is symmetric in the sense that either party can initiate, and the handoff involves not just data but intent. The receiving agent needs to understand not just what data it received but what it is expected to do with it, what success looks like, and what the calling agent needs back.

The distinction matters architecturally because the failure modes are different. An MCP tool that returns an error is a predictable exception with a known schema. An agent that returns a partial result with a confidence flag attached requires the calling agent to make a decision: accept it, retry, escalate, or route to a different agent. The coordination logic required for agent-to-agent interactions is qualitatively more complex than tool invocation.

Here is the mental model I use: MCP is the interface to the agent's hands. A2A is the interface to the agent's collaborators. A well-designed multi-agent system uses both. An agent uses MCP to invoke tools it controls directly, and A2A to delegate to specialist agents it does not control. The two protocols compose cleanly because they operate at different layers: MCP below the agent boundary, A2A above it.

The three-layer protocol stack that is emerging as the consensus architecture reflects this:

**Layer 1, MCP (Tools):** Vertical communication, agent-to-tool, capability discovery and invocation, request-response semantics, JSON-RPC transport.

**Layer 2, A2A (Agents):** Horizontal communication, agent-to-agent, capability negotiation and task delegation, JSON-over-HTTP semantics, Agent Card-based discovery.

**Layer 3, WebMCP (Web):** Browser-native extension of the protocol layer, enabling agents to interact with web surfaces and browser-resident tools.

Teams that understand all three layers can design systems where each layer handles what it is suited for. Teams that conflate the layers will keep encountering coordination failures they cannot diagnose because they have misattributed the problem.

---

## A2A Architecture: Agent Cards and Task Delegation

![Agent Cards, delegation lifecycle, and negotiation](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/a2a/0003.png)

Understanding A2A requires understanding three architectural primitives: Agent Cards, task delegation, and result negotiation. These are not features. They are the load-bearing elements of the protocol. Getting them wrong means the protocol does not deliver its value.

### Agent Cards

An Agent Card is a structured declaration of what an agent can do, what it needs, and what constraints apply to engaging it. It is served at a well-known endpoint, typically `/.well-known/agent.json`, so that any agent or orchestration layer that knows the endpoint can discover the agent's capabilities without prior coordination.

A minimal Agent Card contains:

- **Name and description:** What this agent is and what problem space it operates in
- **Capability declarations:** The specific tasks the agent can accept, with input and output schemas for each
- **Authentication requirements:** What credential or identity the calling agent must present
- **Cost and latency indicators:** Expected resource consumption per task type, which is critical for orchestrators making routing decisions under budget constraints
- **Supported modalities:** Whether the agent can process text, images, structured data, or some combination
- **Failure contract:** What the agent returns when a task cannot be completed: error codes, partial results, escalation signals

The Agent Card is architecturally significant because it moves capability knowledge from implicit (a developer reading documentation and hardcoding a schema) to explicit (a machine-readable declaration that agents can reason over at runtime). This is the same shift MCP made for tools, applied to the agent layer.

An orchestrator with access to a registry of Agent Cards can make dynamic routing decisions based on capability matching, current load, cost constraints, and latency requirements, all without any hardcoded routing logic. This is the foundation of adaptive orchestration.

### Task Delegation

A2A task delegation follows a defined lifecycle: creation, execution, streaming updates, and completion. The calling agent sends a task request that references the capability being invoked, provides the input payload in the schema declared by the Agent Card, includes an idempotency key for safe retry, and optionally specifies a callback endpoint for asynchronous result delivery.

The receiving agent acknowledges receipt and returns a task ID. The calling agent can poll for status or receive streaming updates if the task is long-running. When the task completes, the result is returned in the schema declared by the Agent Card for that capability.

The idempotency key is not a nicety; it is essential for production correctness. In distributed multi-agent systems, network partitions and timeouts mean that a calling agent may not know whether a task it submitted was received and executed. Without idempotency, retry logic produces duplicate actions. With it, the receiving agent can recognize a resubmission and return the original result without executing the task twice.

### Result Negotiation

A2A supports result negotiation: the ability for a receiving agent to indicate that a task can be completed but not in the exact form requested. This is one of the features that distinguishes agent-to-agent communication from tool invocation.

A specialist agent might indicate that it can deliver a result with 85% confidence now or with 99% confidence in thirty seconds, and the calling agent decides which trade-off serves its goal. An agent might indicate that the input it received contains ambiguity and request clarification before proceeding. An agent might indicate that it completed part of a multi-step task and needs a human decision before proceeding further.

None of these interactions are possible with request-response tool semantics. They require a protocol that treats both parties as active reasoners. A2A provides that.

---

## The N-Squared Problem and Orchestration Layers

![N-squared connectivity and hub-and-spoke orchestration](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/a2a/0004.png)

A2A solves the inter-agent protocol problem. It does not solve the inter-agent connectivity problem. These are related but distinct.

Consider a system with ten specialist agents. If every agent maintains direct peer-to-peer connections to every other agent it might need to communicate with, you have potentially ninety bilateral connections. Each connection requires its own authentication configuration, its own retry logic, its own monitoring, and its own failure handling. At ten agents, this is manageable if painful. At twenty agents, the three hundred eighty connections required become operationally unsustainable. At fifty agents (not an unreasonable number for an enterprise multi-agent deployment), the number of potential connections exceeds two thousand four hundred.

This is the N-squared connectivity problem, and it is the reason that naive A2A deployments fail at scale. The protocol is correct. The topology is wrong.

The solution is an orchestration layer that sits above the A2A protocol and manages connectivity on behalf of all agents. Rather than each agent maintaining bilateral connections to peers, every agent has a single connection to the orchestrator. The orchestrator maintains the routing table, enforces capability-based routing decisions, handles authentication for inter-agent calls, monitors task delegation across agent boundaries, and implements retry and fallback logic centrally.

This architecture has a name in network engineering: it is a hub-and-spoke topology, and it is the same structural answer that HTTP proxies, service meshes, and API gateways provide in their respective problem domains. The orchestration layer for A2A is the moral equivalent of a service mesh for multi-agent systems: it abstracts the complexity of peer-to-peer connectivity while preserving the protocol semantics that make each agent's interactions predictable.

There is a cost to this architecture. The orchestrator becomes a single point of failure and a potential bottleneck. The standard mitigations apply: the orchestrator should be stateless where possible so it can be horizontally scaled, critical coordination state should be externalized to a durable store, and failure of the orchestrator should trigger graceful degradation rather than hard failure for in-flight tasks.

The teams that skip the orchestration layer because it feels like overhead will encounter the N-squared problem once their agent count crosses ten. The teams that build it deliberately at the start of their multi-agent journey will find that it pays compound returns as the system grows.

### What Most Teams Get Wrong

The most common mistake I see is building peer-to-peer agent connectivity because it is the path of least resistance at the start. Two agents need to talk, so they talk directly. Three agents, same approach. By the time the system has six or seven agents, the team discovers that the connectivity graph has become a maintenance liability, but they are already deep into a pattern they cannot easily unwind without a major refactor.

The right time to introduce the orchestration layer is before you need it. The decision point is not "we have too many connections now." The decision point is "we are building a system that will eventually have more than three agents." At that scale, the orchestration layer is not overhead; it is the architecture.

---

## Security in Agent-to-Agent Communication

![Identity, delegation chains, and zero-trust between agents](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/a2a/0005.png)

Any reader who followed the [MCP security analysis](https://kranthib.github.io/tech-pulse/gen-ai/mcp.html) will recognize the pattern that emerges when a new inter-agent communication protocol enters wide adoption: the protocol design is clean, the security model is underdeveloped, and the attack surface expands faster than the community's awareness of it.

A2A is meaningfully more security-aware than early MCP was. The protocol includes authentication requirements in the Agent Card specification, mandates identity presentation in task delegation requests, and provides a structured mechanism for agents to verify the identity of calling agents before accepting tasks. These are the right primitives. They are not sufficient on their own.

### Identity at the Agent Boundary

The first security question in any A2A deployment is: how does a receiving agent verify that the caller is who it claims to be? Agent Cards declare authentication requirements, but the protocol does not enforce a specific authentication mechanism. Teams implement JWT-based bearer tokens, mTLS, or API key authentication depending on their existing infrastructure.

The choice matters. API keys are the easiest to implement and the most vulnerable: they are static secrets that can be stolen, shared, or leaked. JWT tokens are better because they are short-lived and cryptographically signed, but they require a functioning token issuance and validation infrastructure. mTLS is the strongest mechanism because it requires both parties to present valid certificates and verifies identity at the transport layer, but it adds operational complexity and requires a certificate management system.

For enterprise deployments, the right answer is mTLS between agents that cross trust boundaries, combined with JWT for intra-trust-boundary delegation. This is the same layered identity model that modern zero-trust network architectures use, applied to the agent layer.

### The Delegation Chain Problem

A2A enables multi-hop delegation: Agent A delegates to Agent B, which delegates to Agent C. Each hop is a legitimate A2A interaction. But the security question that emerges in multi-hop scenarios is: does Agent C know that it is ultimately serving a request that originated with Agent A? Does it care?

In many cases, it should care. If Agent C controls access to sensitive data, it needs to know not just that Agent B is authorized to request that data, but that the original task that triggered the chain is one that a legitimate human or system initiated. A compromised Agent B can issue valid A2A requests to Agent C while serving a malicious objective that Agent A and the original user would never have authorized.

The solution is delegation chain preservation: each hop in the chain includes the identity and authorization scope of the originating request, cryptographically bound so that downstream agents can verify the chain has not been tampered with. This is analogous to how OAuth 2.0 delegation works for human user sessions: the token at every hop carries evidence of the original grant.

Most teams do not implement delegation chain preservation in their first A2A deployment. They implement point-to-point authentication for each hop and assume that if each individual hop is authenticated, the chain is secure. It is not, and the gap becomes exploitable when an agent in the middle of the chain is compromised or manipulated through adversarial input.

### Zero-Trust Between Agents

The zero-trust principle (never trust, always verify) applies to agent-to-agent communication exactly as it applies to human user access to systems. An agent that receives a well-formed A2A request from a known agent identity should not automatically trust that the request represents a legitimate task. It should verify:

1. The calling agent's identity (authentication)
2. Whether the calling agent is authorized to invoke this capability (authorization)
3. Whether the request payload is consistent with the declared task type (input validation)
4. Whether the request pattern is consistent with the calling agent's normal behavior (behavioral verification)

The fourth check is the one that most teams skip. Behavioral verification requires a baseline of what normal inter-agent communication looks like for this pair of agents, and a mechanism to flag or hold requests that deviate significantly. This is operationally more demanding than static authentication, but it is the only control that can detect a compromised agent issuing legitimate-looking requests for malicious purposes.

---

## Implementation Decision Framework

![When to adopt A2A vs simpler coordination](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/a2a/0006.png)

Not every inter-agent interaction warrants A2A. The protocol adds overhead: Agent Card resolution, authentication handshake, task lifecycle management, result serialization. For some interaction patterns, that overhead is justified. For others, simpler mechanisms produce better results with less complexity.

Here is the decision framework I use with engineering teams.

### Question 1: Does this coordination cross an organizational or vendor boundary?

If two agents are in the same codebase, deployed by the same team, and will never be separated, a direct function call or shared message queue may be the right answer. The A2A protocol is designed to handle coordination between agents that do not share a deployment context: different teams, different systems, different providers.

If the coordination crosses a team boundary, a vendor boundary, or a trust boundary, A2A is the right choice. The protocol provides the capability negotiation, authentication, and interoperability guarantees that direct calls cannot provide across boundaries.

**Cross-boundary coordination: use A2A.**
**Intra-boundary, tightly coupled coordination: evaluate simpler options.**

### Question 2: Does the receiving agent need to negotiate capability, or just accept a task?

A2A is designed for interactions where the receiving agent is an active participant that can decline, negotiate, or propose alternatives. If the interaction is a simple dispatch (send input, receive output, no negotiation), a direct API call or a message queue consumer pattern is simpler and more appropriate.

The negotiation surface is A2A's unique value. If you are not using it, you are paying the protocol overhead without receiving the protocol's primary benefit.

**Capability negotiation required: use A2A.**
**Simple dispatch pattern: use a direct call or queue.**

### Question 3: Does coordination frequency justify the protocol overhead?

A2A involves overhead: DNS resolution for the Agent Card endpoint, authentication handshake, task creation, status polling or callback setup. For interactions that happen thousands of times per second, this overhead accumulates. For interactions that happen tens of times per minute, it is negligible.

High-frequency, low-complexity interactions between tightly coupled agents are better served by an internal message queue with a shared schema. Low-frequency, high-complexity interactions between loosely coupled agents are exactly what A2A is designed for.

**Low frequency, high complexity, loose coupling: A2A.**
**High frequency, low complexity, tight coupling: message queue or direct call.**

### The Vendor Lock-In Dimension

One decision factor that teams often underweight is the vendor lock-in implication. A2A is an open standard under the Linux Foundation. Any agent that speaks A2A can coordinate with any other A2A-compliant agent, regardless of which framework or provider built it.

A bespoke inter-agent communication mechanism, by contrast, ties the system to the framework that implements it. Migrating agents to a different framework or provider in the future requires rewriting the coordination logic. At small scale, this is manageable. At enterprise scale, it becomes a migration project.

Teams that implement A2A now, even where a simpler mechanism would work today, are buying optionality. The additional complexity is real, but so is the future flexibility.

---

## Where This Is Heading

The three-layer protocol stack (MCP for tools, A2A for agents, WebMCP for web) is not final. The ecosystem will evolve, and I expect several developments in the coming months.

**Federated Agent Registries** will emerge as teams with large agent portfolios need a way to discover and manage Agent Cards at scale. A single organization might have hundreds of specialist agents. Without a registry, discovering the right agent for a given task requires either manual configuration or a proprietary directory. Open registry standards built on A2A's Agent Card format will provide the infrastructure.

**Agent Identity Infrastructure** will mature significantly. The current state, where teams implement their own authentication mechanisms on top of A2A's authentication requirement declarations, is a temporary condition. Expect to see purpose-built agent identity providers that issue short-lived credentials, enforce delegation chain integrity, and provide audit trails of agent-to-agent authorization grants.

**Cost-Aware Routing** will become a first-class orchestration feature. Agent Cards already support cost and latency indicators. As orchestration layers mature, they will use these indicators to make real-time routing decisions that optimize for cost, latency, and quality simultaneously, routing tasks to cheaper agents when budget is constrained and to higher-quality agents when accuracy requirements are strict.

**Security Observability** for A2A will evolve from custom logging into dedicated tooling that understands the A2A interaction model. Detecting anomalous delegation patterns, enforcing rate limits on inter-agent calls, and auditing the delegation chain for compliance purposes require tooling that understands the protocol semantics. That tooling is being built now.

The teams that are building with A2A today are building on the infrastructure that will define how enterprise multi-agent systems are coordinated for the next several years. The protocol choices made in 2026 will be the migration projects of 2028 for teams that got them wrong.

---

## Practical Starting Point

For teams that are currently running multi-agent systems without A2A, the migration path does not require a full rewrite. The practical starting point is three actions:

**Audit your current inter-agent communication.** Identify every place where one agent hands work to another. Classify each interaction: direct function call, shared queue, bespoke HTTP, or already using A2A. The audit reveals the surface area.

**Identify boundary crossings.** From the audit, identify which inter-agent interactions cross team, vendor, or trust boundaries. These are the highest-priority candidates for A2A adoption. Interactions within a single trust boundary can be upgraded later.

**Implement Agent Cards for your specialist agents.** Even before migrating the calling agents to use A2A, publishing Agent Cards for your specialist agents creates an accurate capability registry that your orchestration layer can consult. This is additive: it does not require changing existing calling logic.

The full migration to A2A for all inter-agent interactions is a multi-sprint effort. The audit, boundary identification, and Agent Card publication are a single sprint's work and provide immediate value.

---

## Closing Thought

The protocol conversation in AI engineering keeps repeating the same pattern. A capability emerges, teams build bespoke solutions, the ecosystem fragments, a standard emerges, and teams that adopted the standard early have clean architecture while teams that built bespoke solutions face migration debt.

MCP went through this cycle for tools. A2A is the standard that closes the same cycle for agent coordination.

The teams building multi-agent systems today without A2A are accumulating coordination debt the same way teams built tool-access debt before MCP. The standard exists. The governance structure is in place. The enterprise deployments are live.

Protocol choices made in 2026 will be migration projects in 2028. Design the stack deliberately now.

---