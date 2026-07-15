---
id: gen-ai/agentic-commerce
title: Agentic Commerce
sidebar_label: Agentic Commerce
previous_page: gen-ai/multi-model-vendor-resilience
next_page: gen-ai/agent-memory
---

<div style="text-align: right;">
    <a href="https://kranthib.github.io/tech-pulse/" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Back to Home →</a>
</div>

# Agentic Commerce: The Payment Layer Nobody Designed For

**A major conversational AI platform launched autonomous checkout with marquee retail partners attached. Within months, the same platform quietly shut it down. The protocol layer underneath kept accelerating the entire time. That gap between the failed product and the thriving infrastructure is the actual engineering story.**

![0000](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/agentic-commerce/0000.png)

---

## The Checkout That Launched and Disappeared

A leading conversational AI assistant launched an autonomous checkout capability, letting the assistant complete a purchase on a shopper's behalf without a separate visit to a merchant's site. Several recognizable retail brands signed on as early partners, spanning categories from handmade goods marketplaces to grocery delivery to big-box general merchandise, a breadth of participation that made the launch read as a genuine cross-industry commitment rather than a narrow pilot. Coverage at launch treated it as the moment agentic commerce stopped being a slide-deck concept and became a shipping product.

Within a relatively short window, the same company discontinued the feature. Adoption had been described, in the surveys tracking it, as low and largely flat from the day it launched to the day it was retired. Only a modest number of merchants had ever integrated it in the first place, a fraction of the ambition the launch coverage implied. The headline product that was supposed to prove agentic commerce had arrived instead became the first widely discussed cautionary tale in the category.

This would be a forgettable story about one company's product decision if it were an isolated data point. It is not. It is the leading edge of a pattern worth understanding carefully before you build a roadmap around the assumption that consumers are ready to let an agent spend their money on their behalf, unsupervised, as a matter of daily habit.

What makes this genuinely interesting for engineering leaders is not the failure itself. It is what did not slow down while that failure was unfolding. In the same stretch of time that consumer adoption of agentic checkout stayed flat, the infrastructure underneath agentic commerce, the protocols, the payment network integrations, the fraud and authentication layers, kept shipping at a pace that had nothing to do with whether ordinary shoppers wanted an agent to buy their dog food. A major payment network embedded its authentication and settlement capability directly into a leading conversational assistant. Two competing commerce protocols, backed by different coalitions of technology and retail companies, both reached production maturity. An HTTP status code reserved for payment functionality decades ago and never used finally found its purpose as the backbone of machine-to-machine transactions.

The story here is not "agentic commerce is a hype cycle that already burst." It is that the layer where real, durable engineering work is happening and the layer where consumer attention lives are currently two different layers, moving at two different speeds, and conflating them is the most common strategic mistake I am seeing right now.

![0001](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/agentic-commerce/0001.png)

---

## Why Consumer Adoption Lagged While Infrastructure Accelerated

It is worth being precise about what actually failed and what did not, because the two are frequently discussed in the same breath as though they were a single, unified story.

What failed was a specific consumer-facing product bet: that shoppers, given a conversational interface capable of completing a purchase autonomously, would prefer that experience over a traditional checkout flow they already trust and understand. The data on this bet has been consistent and unflattering. Surveys tracking consumer interest found adoption concentrated in a narrow demographic slice, interest described as lukewarm even among the more receptive segments, and no evidence of the experience displacing traditional checkout at any meaningful scale.

What did not fail, and in fact accelerated through the exact same period, was the infrastructure layer beneath that consumer experience. A payment network's fraud and bot-detection capability was extended specifically to authenticate agentic shopping traffic, a problem that did not exist as a named category before agents began browsing and buying. A rival commerce protocol backed by a different coalition of retail and technology partners reached general availability, aimed less at consumer chat interfaces and more at giving any merchant a standard way to expose their catalog and checkout flow to any agent, regardless of which assistant the shopper happens to be using. A digital wallet provider extended instant-checkout functionality into a competing conversational search product, targeting a different distribution channel than the one that had just been discontinued elsewhere.

The distinction that matters architecturally is this: consumer adoption of agent-driven shopping is a product-market-fit question, and it is currently answered, honestly, with "not yet, and not obviously coming soon." Infrastructure maturity for machine-initiated commerce is an entirely separate engineering question, and it is answered with "already happening, accelerating, and largely independent of the consumer answer." Teams that build their roadmap around the first question, betting on consumer demand that has not materialized, are building on the less certain foundation. Teams that build around the second question, treating agentic payment infrastructure as a capability worth having regardless of consumer checkout adoption, are building on ground that keeps getting more solid every quarter.

![0002](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/agentic-commerce/0002.png)

---

## The Protocol Layer: A Standards Contest With Real Stakes

Underneath both the failed consumer product and the surviving infrastructure sits a genuine standards contest, and understanding its shape matters more for engineering planning than any single product launch does.

For roughly three decades, an HTTP status code existed in the specification for exactly this purpose and was never implemented: code 402, reserved for "Payment Required." It sat unused because the traditional payment rails it would have needed to interoperate with assumed a human was present to authorize a transaction, something that browser-based commerce never fundamentally required a machine-native alternative for. That assumption is precisely what agentic commerce breaks, and the dormant status code has become the technical anchor for a new payment scheme built specifically for machine-to-machine transactions, where an API endpoint can require payment before releasing a response and an agent can satisfy that requirement programmatically, without a human clicking anything.

Running alongside this machine-payment protocol is a second, competing family of standards aimed at a different part of the same problem: how a merchant describes its catalog, pricing, and checkout flow in a way that any capable agent, regardless of vendor, can discover and act on without bespoke integration work per assistant. One major protocol in this family emerged from a partnership between a large e-commerce platform and a frontier AI lab, oriented around checkout specifically. A second, backed by a different coalition spanning a major search and cloud provider alongside a leading commerce platform, took a broader "universal commerce" framing, aimed at being the connective layer between any agent and any merchant rather than a single assistant's checkout feature.

Neither of these commerce-description protocols has definitively won, and the honest engineering position right now is that neither is likely to fully displace the other in the near term. They target overlapping but distinct integration surfaces, and the coalitions backing each have enough market weight that a genuine standards war, rather than a quick consolidation, is the more likely near-term outcome. For a merchant or platform engineering team, this means the defensible move is building an abstraction layer that can speak to either protocol rather than betting the architecture on a single winner. This is precisely the same lesson multi-provider AI infrastructure has already taught engineering teams in an adjacent context: whenever a category has two well-funded, well-adopted standards competing simultaneously, the safe architectural choice is the one that does not require picking a side before the market has.

A further wrinkle worth naming explicitly is that these protocols are not simply competing implementations of the same idea. They differ in what they assume about where the checkout logic lives. One protocol family assumes the assistant itself orchestrates the full purchase flow end to end, treating the merchant largely as a catalog and fulfillment backend. The other assumes the merchant retains more control over the checkout experience itself, exposing structured data for discovery and comparison while keeping the actual transaction closer to infrastructure the merchant already operates and trusts. These are not cosmetic differences. They imply different data-sharing boundaries, different points where a merchant can enforce its own fraud and pricing rules, and different answers to who is actually the system of record for a given transaction. A team integrating with only one protocol family is making an implicit bet on which of these two philosophies of control will matter more to their specific merchant base, and that bet deserves to be made deliberately rather than by default.

It is worth adding that this pattern, two philosophically distinct protocols competing under a shared label, is not unique to commerce. The same divergence between assistant-orchestrated and merchant-orchestrated control shows up in how different agent frameworks handle tool execution more broadly, and the resolution tends to arrive the same way each time: not through one philosophy proving definitively correct, but through the market segmenting, with each approach becoming the default in the contexts where its underlying assumption about who should hold control actually fits. Commerce is likely to follow that same arc rather than a clean, winner-take-all resolution.

![0003](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/agentic-commerce/0003.png)

---

## The Payment Network Response: Trust Infrastructure for Non-Human Buyers

The payment networks themselves, the companies that have spent decades building the trust and fraud infrastructure underlying nearly every consumer transaction, have not been passive observers of this shift. Their response is worth studying separately from the protocol contest above, because it addresses a distinct and arguably harder problem: how do you extend decades of fraud detection, card-not-present risk scoring, and dispute resolution, all of it built on assumptions about human behavioral signals, to a buyer that is, by construction, not human.

A major card network partnered with a content delivery and bot-detection specialist specifically to build an authentication layer for agentic shopping traffic, addressing a problem that is genuinely new: traditional bot detection exists to block automated traffic, while agentic commerce requires the opposite capability, distinguishing a legitimate, user-authorized purchasing agent from a fraudulent scripted attack, when both present as automated, non-human traffic hitting a checkout endpoint. A second major network built a named "agent pay" capability specifically for merchant integration, piloting it with retail partners in newer markets before wider rollout. Most significantly, one network embedded its payment authorization capability directly inside a leading conversational assistant, allowing a consumer to link a card, set a spending limit, and let the assistant complete purchases at any accepting merchant without a separate checkout flow for that specific integration.

The engineering substance underneath all of this is a new category of identity and authorization problem: proving that a specific autonomous agent, acting on a specific authenticated human's behalf, within a specific spend limit the human set and can revoke at any time, is the party attempting a transaction. This is a genuinely different problem from either traditional card-present authentication or the API-key-based authentication that machine-to-machine systems have used for API access historically. It borrows elements from both and is not fully solved by either.

Consider what each existing model gets partially right and where it breaks down. Card-present and card-not-present fraud models are built around behavioral signals: typing cadence, device fingerprinting, purchase history patterns, geolocation consistency, all of it designed to distinguish a genuine cardholder from someone who has stolen their credentials. An agent has none of these signals in any meaningful sense; it does not type with a cadence, and its device fingerprint is identical across every transaction it ever initiates, legitimate or not. API-key authentication, by contrast, is built around proving that a specific piece of software has a specific credential, which solves the "is this the agent we authorized" question cleanly but says nothing about whether the human standing behind that agent actually wants this specific transaction to happen, at this specific price, from this specific merchant, right now.

The trusted-agent authentication models now emerging attempt to synthesize both: a cryptographically verifiable link between the human's original authorization, the specific agent instance acting on it, and the specific transaction being attempted, checked against the spend parameters the human configured, with the payment network sitting in the position of verifying the entire chain rather than any single link in it. This is meaningfully harder to get right than either of the models it draws from, and it is precisely the layer where the payment networks, who have spent decades building exactly this kind of trust infrastructure for humans, have a genuine structural advantage over any individual AI platform trying to solve authentication on its own.

![0004](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/agentic-commerce/0004.png)

---

## The Real Engineering Problem: Attribution, Liability, and Spend Control

Strip away the product launches and the protocol contest, and the actual unresolved engineering and governance problem in agentic commerce is not "can an agent complete a purchase." That part works today, across multiple protocols and payment networks. The unresolved problem is what happens in the much less glamorous scenario: the agent buys the wrong thing, buys too much of it, or gets manipulated by a malicious merchant listing into completing a transaction the human never would have authorized if they had seen it themselves.

Three design requirements sit underneath every credible agentic commerce integration, and none of them are solved by the payment protocol alone.

**Spend authorization has to be structural, not conversational.** A spend cap that exists only as an instruction in a system prompt is not a control; it is a suggestion the agent's own reasoning is responsible for honoring. A credible implementation enforces spend limits, merchant category restrictions, and per-transaction approval thresholds at the payment authorization layer itself, the same way a corporate card program enforces limits at the network level rather than trusting the cardholder's judgment alone. Anything less is a control that exists on a slide deck and fails the first time the agent's reasoning is wrong, manipulated, or simply confused about the price of something.

**Attribution has to survive the full transaction chain.** When an agent completes a purchase through a protocol layer, through a payment network's authentication service, settled by a merchant's payment processor, the record of who actually authorized that specific transaction, at what spend limit, under what standing instruction, needs to be reconstructable after the fact by every party in that chain, not just the first hop. This is structurally the same delegation-chain integrity problem that agent-to-agent coordination protocols have had to solve for non-commerce use cases, applied here to money rather than data.

**Liability allocation has to be explicit before the first disputed transaction, not after.** When an agent purchases the wrong item, purchases from a fraudulent listing it should have flagged, or is manipulated by adversarial content injected into a product description, the question of who bears that loss, the platform that built the agent, the payment network that authorized the transaction, the merchant that listed the product, or the consumer who set up the standing authorization, does not currently have a settled, consistent answer across the industry. Engineering teams building agentic commerce integrations without an explicit, contractually documented answer to this question are building on a foundation their own legal and risk teams have not yet actually agreed to stand behind.

![0005](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/agentic-commerce/0005.png)

---

## A Worked Example: Evaluating a B2B Procurement Agent Integration

The abstract version of these three requirements is easier to nod along with than to actually implement. Walking through a concrete scenario makes the gap between having a policy and having a working system more visible.

Consider an engineering team building an internal procurement agent, one authorized to reorder standard office and operational supplies from a defined set of approved vendors whenever inventory signals indicate a reorder is needed, without a human approving each individual purchase order. This is a realistic, currently buildable use case, and it sits squarely in the machine-to-machine category rather than the stalled consumer checkout category, which is precisely why it is a more useful example than a retail scenario would be.

The first design decision is where spend authorization actually lives. The naive implementation gives the agent a system prompt instructing it to stay under a monthly budget and trusts the agent's own arithmetic and judgment to enforce that. The credible implementation instead issues the agent a scoped payment credential, provisioned through whichever machine-payment protocol the finance function has adopted, with a hard spend ceiling, an approved-merchant allowlist, and a per-transaction maximum enforced at the credential level itself, so that a reasoning failure, a prompt injection from a compromised vendor catalog, or a simple miscalculation cannot result in a transaction the credential itself does not permit. The distinction is the same one that separates a deny-by-default network firewall rule from a comment in a code review asking a developer to please not open that port.

The second design decision is attribution. Every transaction the procurement agent initiates needs a record that survives the full chain: which standing authorization permitted it, which specific inventory signal triggered the reorder decision, what alternative vendors or quantities the agent considered and rejected, and a timestamped link between the agent's reasoning trace and the actual payment authorization that resulted. Without this, a finance team auditing a disputed or unusually large charge six weeks later has no way to reconstruct why the agent believed the purchase was justified, and is left trusting either the agent's own post-hoc explanation or nothing at all.

The third design decision is the liability conversation that has to happen before the integration goes live, not during the first vendor billing dispute. If the procurement agent is deceived by a compromised or fraudulent vendor listing into paying an inflated price, or into ordering from an unauthorized substitute vendor whose catalog was somehow injected into the agent's consideration set, the organization needs a pre-agreed answer for whether that loss is absorbed internally, disputed with the payment network under existing fraud provisions, or pursued against the vendor platform directly. Waiting until the dispute actually happens to have this conversation for the first time reliably produces a worse outcome than having it in advance, if only because the incentives of every party involved shift once real money is already on the table.

None of these three moves requires exotic technology. Each is a deliberate design decision with a clear owner, and each is meaningfully easier to make correctly before the agent is authorizing real transactions than to retrofit afterward.

---

## What Most Teams Get Wrong

The most common mistake right now is treating agentic commerce as a consumer checkout feature decision: should our product add a "let the assistant buy it for you" button, framed as a race to match whichever competitor moved first.

This framing is backwards for two reasons. First, the actual data on the highest-profile consumer implementation of exactly this feature shows adoption that never left the ground, which should be a serious caution against assuming a checkout-button feature is the valuable part of this category. Second, and more importantly, it points engineering investment at the layer with the least durable technical substance, a conversational checkout UI, and away from the layer that is actually accumulating engineering value regardless of consumer sentiment: standardized, protocol-level machine-to-machine payment capability that any merchant, any B2B integration, and any agent, not just a consumer shopping assistant, can build on.

The second, closely related mistake is assuming the protocol contest between the commerce-description standards will resolve quickly enough that picking one now is a low-risk bet. The market signal so far points toward sustained competition between well-funded coalitions rather than fast consolidation, which makes an abstraction layer over both protocols the more defensible engineering investment, even though it is a less exciting roadmap item than declaring allegiance to one standard.

The third mistake is treating spend control and liability allocation as launch-blocking legal review items to be handled once, rather than as ongoing engineering and contractual work that needs to evolve as the protocol landscape itself evolves. A spend-control implementation that was adequate when your only integration was a single payment network's checkout capability needs active reassessment the moment you add a second protocol, a second network, or expand into a new transaction category, because the attribution chain and liability allocation both change shape with every new integration point added.

The fourth mistake, and the subtlest one, is benchmarking success against the wrong baseline. Teams that measured the discontinued consumer checkout feature against "did it displace traditional checkout" were asking a question the data was never going to answer favorably in the near term. A more useful baseline, and the one the surviving infrastructure investments are implicitly being measured against, is simply "did this reduce integration friction for merchants and agents that were already going to transact through some channel." Judged against that baseline, the protocol and authentication layer has already delivered real value, even while the consumer product built on top of it did not.

![0006](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/agentic-commerce/0006.png)

---

## A Decision Framework for Where to Invest Right Now

For engineering leaders trying to decide where to put resources in this category, the distinction that matters most is between consumer-facing checkout experiences and B2B or machine-to-machine payment infrastructure, because the evidence on maturity and durability is meaningfully different for each.

**If your business is consumer-facing retail or commerce**, the defensible move is instrumenting your existing checkout to be discoverable and transactable by external agents through the emerging commerce-description protocols, building the capability without betting your roadmap on consumers actually choosing to transact conversationally in large numbers any time soon. This is a hedge, not a bet: it costs relatively little to expose a standards-compliant integration surface, and it means you are not locked out if adoption does eventually accelerate, without requiring you to believe it will. Concretely, this usually means exposing structured product and pricing data through whichever protocol your largest customer segment is most likely to encounter, instrumenting the integration to measure actual agent-driven traffic against actual agent-driven conversion, and resisting the temptation to build a bespoke conversational checkout experience before the data justifies the investment.

**If your business involves agent-to-agent or agent-to-API transactions**, machine-initiated payments for compute, data, or automated procurement, the machine-payment protocol layer built around the revived payment-required status code is the more directly relevant investment, and it is maturing independent of anything happening in consumer retail. This is genuinely new infrastructure solving a genuinely new problem, and the adoption curve here looks nothing like the stalled consumer checkout story. Concretely, this means treating payment authorization as a first-class part of your agent architecture from the outset, with scoped credentials and hard spend ceilings enforced outside the agent's own reasoning, rather than retrofitting payment capability onto an agent that was originally designed only to read and recommend.

**Regardless of which side you sit on**, the spend control, attribution, and liability questions above are not optional homework to defer. They are the actual hard engineering problem in this category, and they need dedicated ownership, explicit design decisions, and contractual clarity before the first real transaction, not retrofitted after the first disputed one. A useful forcing function is to require, as a condition of launch, a one-page document naming who owns each of the three questions, what the current answer is, and when it was last reviewed. If that document does not exist, the integration is not ready for real money, regardless of how well the checkout flow itself demos.

---

## Where This Is Heading

The consumer checkout story will likely continue to be uneven for a while. Interest is real but not yet broad, and the one high-profile failure so far is unlikely to be the last, because the underlying question, whether people want to hand purchasing decisions to a conversational agent rather than a familiar checkout flow, has not actually been answered yes by the market yet, regardless of how many payment networks build the rails to support it.

The infrastructure story looks different. Authentication and trust frameworks purpose-built for non-human buyers will keep maturing, because fraud and dispute costs create direct financial pressure to solve that problem regardless of consumer sentiment. The standards contest between competing commerce-description protocols will likely continue for some time before any real consolidation, which argues for architectural patience rather than early commitment from teams building on top of it. And the unresolved liability and attribution questions will increasingly show up in actual contract negotiations and, eventually, in actual disputes that set real precedent, well before any regulator writes a comprehensive rule for the category.

A related development worth watching is how the B2B side of this category is likely to mature faster and more quietly than the consumer side ever did. Procurement, supply chain replenishment, and automated vendor payments are all scenarios where the buyer is already a business rather than an individual consumer, where spend controls and audit trails are already an expected part of any financial system rather than a novel add-on, and where the "does the buyer trust an agent" question barely applies, since the agent is acting under an internal delegation of authority the business itself configured, not persuading a skeptical individual consumer to change their shopping habits. This is precisely the segment where the checkout-button framing that dominates consumer coverage of this category is least relevant, and where the actual engineering substance, protocol integration, spend governance, attribution, is most directly rewarded.

There is also a talent dimension worth naming. Very few engineering organizations currently have anyone whose job explicitly includes owning agentic payment integration, spend governance, and the associated liability conversations with legal and finance. This ownership gap mirrors a pattern seen repeatedly whenever a genuinely new capability crosses from experimental to production: the organizations that assign clear ownership early, before the first real transaction rather than after the first real dispute, consistently build more defensible systems than the ones who leave it as a shared responsibility that nobody quite owns.

The engineering leaders who separate these two stories, treating consumer adoption as an open, unresolved product question and infrastructure maturity as an accelerating, largely independent engineering opportunity, will make better resourcing decisions than the ones chasing whichever headline moved last. The most valuable work in this category right now is not the checkout button. It is the plumbing underneath it, and the plumbing does not care whether the button gets used.

---
