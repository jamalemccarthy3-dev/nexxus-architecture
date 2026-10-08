# Autonomous Automation AI Infrastructure and Orchestrator

**NEXXUS: architecture playbook**

> ### "My time is money. My product is free."
>
> *The core philosophy of this repository.*

> A modular, local-first AI ecosystem made of **22 standalone engines**, one **bridge**, and a private **core**.
> This repository is the *map*, not the territory: you can see exactly how the system is organised, and none of the implementation.

## What it is: in my words, and in formal terms

| In my words | The formal technical equivalent |
|---|---|
| **Autonomous Automation** | **Agentic workflow automation** with bounded autonomy and human-in-the-loop governance |
| **AI Infrastructure** | **Self-hosted, local-first AI infrastructure**: a local model-serving runtime plus a modular multi-engine service platform on a single node |
| **Orchestrator** | **Orchestration layer / control plane**: hub-and-spoke service orchestration through a single gateway, with a policy-enforcement (guardian) layer |
| **The whole system** | **A self-hosted, local-first, multi-engine AI orchestration platform** (SaaS-free, zero-cloud local orchestration) |

**In one sentence:** a **SaaS-free, local-first AI infrastructure**: a **modular multi-engine architecture** with **zero-cloud local orchestration**,
**hub-and-spoke integration through a single gateway**, and **human-in-the-loop governance**, running as a **single-node, vertically scaled** system.

## Distribution model: infrastructure, not handouts

**You are getting the sovereign orchestration framework and its empty utility skeletons. You are not getting proprietary, plug-and-play source code.**

| What you get | What you do not get |
|---|---|
| The **sovereign orchestration framework**: layout, boundaries, principles and the specification | Proprietary, plug-and-play engine source code |
| **Empty utility skeletons**: the folder and file structure of every engine, as placeholders | The internal wiring, configuration or data of the reference build |
| A **proven reference**: proof-of-life receipts from a real, local, cloud-free build | A hand-held tutorial, or a script that "just works" |

**The engineering standard.** The architecture is engineered to stand on its own and to run entirely on local hardware with no cloud: the reference build does exactly
that (see the proof-of-life receipts). But a skeleton is only a skeleton. **The implementation, and the execution of it, depend entirely on the builder's capability.**

**Reality check.** This is strictly local-first infrastructure with empty utilities. If you rely on cloud crutches, outsourced APIs, or a hand-held tutorial script,
**this build is not for you.** If you can build, it is the foundation to build on.
If you would rather pay the architect than do the work, see **Industrial Build & Enterprise Licensing** below.

## The assignment: command your own local AI

This repository is an **assignment, not a handout**. The framework is designed to stand up at its **bare minimum** (one gateway, one engine, one liveness check) and to grow from
there, and you do not need anyone's custom code to do it. You need the specification, a local AI and the willingness to put in the work: **wire up the utilities by working directly with your
own local AI**. By the end you will know how to command a local AI infrastructure, because you built it, and the architecture will have proved itself on your own machine.

Start here: [`docs/ASSIGNMENT.md`](docs/ASSIGNMENT.md), including a ready-to-adapt instruction template for your local AI.

## Original by design (a bespoke, from-scratch custom architecture)

**Built from the ground up. Not a fork, not a template, not a wrapper around someone else's agent framework** (no LangChain-style orchestration layer underneath).

Every engine and the core shown here was designed and written from scratch for this project, around one builder's needs, starting from a blank folder. It stands on
well-established architectural ideas (**modularity, a single API gateway, separation of concerns**) and the particular **composition** is its own:
22 isolated engines behind one bridge port, a private core, and a public facade that shows the structure while the implementation stays private.
You are looking at a **completely independent, sovereign framework**, not a configuration of a product you can buy.

## Free, local-first, and yours (SaaS-free local AI infrastructure)

**No subscriptions. No required cloud service. No vendor you cannot walk away from.**
Cutting the cloud cord means a **SaaS-free, zero-cloud, self-hosted** stack: **vendor-neutral, with no lock-in**.

This is infrastructure designed to give a developer **computational sovereignty** (**data and compute sovereignty, on-prem / edge by design**): it runs on your
own hardware, it is built from free and self-hosted parts, and nothing in it is load-bearing on a service that someone else can switch off or reprice. Any connection to
the outside world is optional and is always your decision. It is built in the spirit of open source: the architecture is published for anyone to study, copy and build on
(see the licence below).

## What is shared, and what is not

I am giving away the **sovereign, local-first infrastructure design**, completely free, to prove it can be done. To be absolutely clear about what that means:

| Provided here, free | Not provided |
|---|---|
| The infrastructure layout: engines, core, bridge, dashboard (the **reference architecture**) | The engine source code |
| The public facade: every folder and file name, as a map (an **interface-only publication**) | The proprietary internal bridge-wiring files: these stay **strictly private, personal IP** |
| The architecture, its boundaries and the reasoning behind them | Private configuration, data and secrets |

**You will structure and write your own underlying code.** This repository gives you the blueprint and the proof that the approach works; the
building is yours to do.

## Why this repository exists

Most architecture write-ups are either slide decks with no substance or source dumps with no map. This one publishes the **shape** of a real,
running system - its folders, its boundaries, its separation of concerns - and deliberately withholds the code behind it.

That is the **facade / core separation** (the **Facade pattern applied at repository level**: public interface, private implementation, **information hiding**):

| | Public (this repo) | Private (the real system) |
|---|---|---|
| What you see | Folder layout, names, boundaries, this overview | Implementation, configuration, data, secrets |
| Purpose | A reference for modular, decoupled design | The working system |
| Every source file here | A one-line placeholder | The real code |

## The idea in one picture (how the engines snap together)

```
   +--------+  +--------+  +--------+  +--------+           +--------+
   | engine |  | engine |  | engine |  | engine |   . . .   | engine |      22 standalone engines
   +---+----+  +---+----+  +---+----+  +---+----+           +---+----+      (each one is a self-contained folder)
       |           |           |           |                    |
       |    engines never talk to each other directly            |
       v           v           v           v                    v
   +-------------------------------------------------------------------+
   |                          B R I D G E   P O R T                    |   <- the one and only door
   +----------------------------------+--------------------------------+
                                      |
                +---------------------+---------------------+
                |                                           |
         +------+-------+                            +------+-------+
         | NEXXUS core  |                            |  dashboard   |
         +--------------+                            +--------------+
```

**How the engines snap together:** a **modular multi-engine architecture** with **zero-cloud local orchestration**. Every engine connects through one
**single gateway (the bridge port)** in a **hub-and-spoke topology**, so there is no engine-to-engine coupling.

## Proof of life: verified local multi-engine orchestration

No cluster. No cloud service required. One machine. These are not mock-ups: both receipts below were **generated from real runs** by a capture script that refuses to
write anything if a single check fails. Only results are shown, never code.

These receipts describe the **reference build**. They are evidence that this architecture runs locally, with no cloud; they are not a claim that this repository is runnable.

<!-- generated from real runs; do not edit by hand -->

**Receipt 1 - live multi-engine synchronisation.** Captured from the running reference build on a single local machine.

```
NEXXUS MESH  -  proof of life  -  captured 2026-10-08 08:38

[PASS] axis-cloud          signed heartbeat verified   LIVE
[PASS] axis-core           signed heartbeat verified   LIVE
[PASS] axis-curator        signed heartbeat verified   LIVE
[PASS] axis-diagnostic     signed heartbeat verified   LIVE
[PASS] axis-drive          signed heartbeat verified   LIVE
[PASS] axis-integrity      signed heartbeat verified   LIVE
[PASS] axis-link           signed heartbeat verified   LIVE
[PASS] axis-llm            signed heartbeat verified   LIVE
[PASS] axis-logic          signed heartbeat verified   LIVE
[PASS] axis-omni           signed heartbeat verified   LIVE
[PASS] axis-phonetic       signed heartbeat verified   LIVE
[PASS] axis-port           signed heartbeat verified   LIVE
[PASS] axis-SandM          signed heartbeat verified   LIVE
[PASS] axis-search_engine  signed heartbeat verified   LIVE
[PASS] axis-sweep          signed heartbeat verified   LIVE
[PASS] axis-triage         signed heartbeat verified   LIVE
[PASS] axis-validator      signed heartbeat verified   LIVE
[PASS] axis-vantage_point  signed heartbeat verified   LIVE
[PASS] axis-video_creator  signed heartbeat verified   LIVE
[PASS] axis-vision         signed heartbeat verified   LIVE
[PASS] render              signed heartbeat verified   LIVE

COMPONENTS LIVE        21 / 21
MANIFEST VERIFIED     21 / 21
MESH-ENABLED          21 / 21
PACKETS VERIFIED      3404
PACKETS REFUSED       0
GUARDIAN STATE        CLEAR
```

**Receipt 2 - autonomous pipeline orchestration and guardian.** The master suites, run fresh against the reference build for this capture.

```
NEXXUS MASTER SUITES  -  captured 2026-10-08 08:38

[PASS] Guardian: signing, replay, tamper and drift refusal          131 / 131
[PASS] Scoped key custody and grants                                 39 / 39 
[PASS] Human-approved autonomous tool intake                         47 / 47 
[PASS] Dependency and key provisioning loop                          72 / 72 
[PASS] Background job pipeline orchestration                         42 / 42 
[PASS] Zero-cloud dashboard: no external loads, bundled 3D library   25 / 25 
[PASS] Public-facade leak guard                                      26 / 26 

CHECKS PASSED         382 / 382
CHECKS FAILED         0
RESULT                ALL GREEN
```


## Principles

1. **Autonomous engines** (**loosely coupled, process-isolated service modules**). Every engine is a complete folder that stands on its own. Nothing outside it needs to know how it works inside.
2. **One door** (**a single point of ingress: the API-gateway / hub-and-spoke pattern**). Engines do not call each other. Everything that crosses a boundary crosses it at the bridge port, so the whole system has a single
   place to observe, guard and change.
3. **A sovereign core** (**orchestrator / control plane**). The core decides; engines advise and execute. The design goal is that taking one engine away does not stop the others.
4. **Local-first and subscription-free** (**local-first software, SaaS-free, zero-cloud orchestration**). Designed to run on your own hardware, with free, self-hosted components. No subscription and no cloud service is required.
5. **Humans approve growth** (**human-in-the-loop (HITL) governance, approval-gated capability onboarding**). New capabilities are proposed, explained in plain language, and only added after an explicit owner decision.
6. **Structure is public, implementation is private** (**the Facade pattern at repository level**). Boundaries are safe to show. Internals are not.

## Capacity and limits: the hardware envelope

This is a **local, sovereign, zero-subscription powerhouse**, and it runs on **single-machine physics**: the CPU, the RAM and, where you have one, the local GPU set the
ceiling. Think of an "unlimited" mobile plan. You get massive, high-performance capability, but push past a certain threshold of **heavy concurrent local generation** and you hit
the hardware wall.

In technical terms: **resource-bound, concurrency-limited local inference on a single node, scaled vertically** (better hardware, not more machines).

| It is built for | It is not built for |
|---|---|
| **Absolute personal sovereignty** and high-level **autonomous development** on one machine | **Infinite multi-node cloud scaling out of the box**: no horizontal scaling, no cluster scheduler, no cross-machine failover |
| Running with **no subscription or licence fee** | A promise of "zero cost": the hardware and the electricity are yours |

The reference system is a modest desktop: a dual-core CPU, about 8 GB of RAM, integrated graphics and no discrete GPU. It runs every engine and the local models.
That is the floor, not the ceiling. The full envelope is in [`docs/SPECIFICATION.md`](docs/SPECIFICATION.md).

## Why I am sharing it: paying it forward

I am releasing this to pay it forward and to give everyone an opportunity to build. It proves that **independent, sovereign architecture can be done**:
by one builder, on ordinary hardware, without a subscription or a platform behind it.

**You are free to use this open infrastructure.** Take the folder structure, the boundaries and the "engines behind one bridge port" idea, write your
own engines and your own wiring, and make it yours.

**One personal request.** If it works for you, all I ask is that you make a short video acknowledging that the architecture worked and point people
back to this repository, so that everyone watching has the same opportunity to build for free. The video is a request; the **credit and link are a licence
condition** (see Licence, attribution and commercial use below).

## How to read this repository

| Folder | What it is |
|---|---|
| [`engines/`](engines/) | The 22 standalone engines (self-contained **service modules**), one folder each |
| [`core/`](core/) | The NEXXUS core (the **orchestrator / control plane**) |
| [`bridge/`](bridge/) | The bridge side: the server, the shared gateway (**integration hub**) and the guardian |
| [`dashboard/`](dashboard/) | The user interface (**presentation layer**) |
| [`docs/ASSIGNMENT.md`](docs/ASSIGNMENT.md) | The assignment: how to command your own local AI to build and wire the utilities |
| [`docs/SPECIFICATION.md`](docs/SPECIFICATION.md) | The architecture specification: integration path, capacity and limits, what is online and what is not |
| [`STRUCTURE.md`](STRUCTURE.md) | The complete folder and file layout |

Open any file and you will find a single line saying the implementation is withheld. That is expected: the **names and the layout** are the content.

## The engines

| Engine | Label |
|---|---|
| [`S.A.M.U.E.L.-`](engines/S.A.M.U.E.L.-/) | Standalone engine |
| [`axis-SandM`](engines/axis-SandM/) | Standalone engine |
| [`axis-cloud`](engines/axis-cloud/) | Cloud |
| [`axis-core`](engines/axis-core/) | Standalone engine |
| [`axis-curator`](engines/axis-curator/) | Curation |
| [`axis-diagnostic`](engines/axis-diagnostic/) | Diagnostics |
| [`axis-drive`](engines/axis-drive/) | Standalone engine |
| [`axis-integrity`](engines/axis-integrity/) | Integrity checks |
| [`axis-link`](engines/axis-link/) | Standalone engine |
| [`axis-llm`](engines/axis-llm/) | Language models |
| [`axis-logic`](engines/axis-logic/) | Logic and domain modules |
| [`axis-omni`](engines/axis-omni/) | Standalone engine |
| [`axis-phonetic`](engines/axis-phonetic/) | Phonetics |
| [`axis-port`](engines/axis-port/) | Standalone engine |
| [`axis-search_engine`](engines/axis-search_engine/) | Search |
| [`axis-sweep`](engines/axis-sweep/) | Sweep |
| [`axis-triage`](engines/axis-triage/) | Triage |
| [`axis-validator`](engines/axis-validator/) | Validation suite |
| [`axis-vantage_point`](engines/axis-vantage_point/) | Standalone engine |
| [`axis-video_creator`](engines/axis-video_creator/) | Video creation |
| [`axis-vision`](engines/axis-vision/) | Vision |
| [`triad-protocol-module-`](engines/triad-protocol-module-/) | Standalone engine |

## FAQ

**Can I run this?** Not from this repository: it contains the layout, not the code. You are free to use the layout to build your own.

**Why publish it at all?** To share a working example of how a large modular system can be organised (**modular, decoupled, local-first AI architecture**), and to invite discussion about the design.

**Is the real code open?** No. The implementation lives in private repositories and is available only under the Industrial Build agreement (see Industrial Build & Enterprise Licensing).

**Does it scale across many machines?** Not out of the box. It is a single-node, vertically scaled design: more capability means better hardware on the same machine. Scaling out
would be a different architecture that you would design and build yourself.

**Can I copy and build on the design?** Yes. That is the point. See the licence below.

**Why is the code private if the idea is free?** The design is the part that can be shared safely and usefully. The implementation contains private
configuration and wiring that is specific to one machine and one owner.

## Acknowledgments

**Google and Gemini: the core architectural partner.** A tribute to the free intelligence layer that helped collect the thoughts, structure the engine parameters and co-architect this
system from the ground up. Gemini was a **design-time partner**: nothing in the running system depends on it.

**Hugging Face**, the open hub that makes models, datasets and tooling accessible to everyone. **Llama**, the open-weight models from Meta that make serious local inference possible on ordinary hardware.

Together they are the trifecta of the **open and accessible stack** that made sovereign, local-first infrastructure possible.
Product names and marks belong to their owners; their mention here is gratitude, not endorsement by them.

## Licence, attribution and commercial use

**Open for study and integration. Attribution is mandatory.**

This skeletal framework and blueprint (the layout, names and documentation in this repository) are licensed under
[**Creative Commons Attribution 4.0 (CC BY 4.0)**](https://creativecommons.org/licenses/by/4.0/). You may study them, copy them, integrate them and build on
them, **including commercially, with no fee and no royalty**. There is one condition, and it is not negotiable:

> **Any commercial, monetized or profit-driven deployment built on this architecture must credit the original author and name this repository as the
> source of the architecture.**

If you commercialize it, you do so *without reimbursing the author*, and that is precisely why the credit is **strictly required**. In practice:

1. **Credit the original author** (the owner of this repository).
2. **Link to this repository** as the source of the architecture, wherever you present the product or its documentation (site, docs, README, launch material).
3. **Indicate what you changed.**

A suitable credit line:

> *Architecture based on "NEXXUS: Autonomous Automation AI Infrastructure and Orchestrator" by the original author (link to this repository), licensed under CC BY 4.0.*

Failure to give credit ends your right to use the material under the licence (CC BY 4.0, section 6). Using it without credit is not "borrowing the idea": it is use
without permission.

**Authorship record.** The dated, public commit history of this repository is a timestamped record of the authorship and first publication of this architecture.
It stands as public evidence of who published this design, and when.

**What the licence does not cover.** The private implementation, including the internal bridge-wiring files, is not covered by this licence, is not published,
and remains private personal IP; it is available only under the Industrial Build agreement below. Publishing this repository does not transfer ownership of anything: the author keeps the copyright.

## Industrial Build & Enterprise Licensing

**Build it yourself, free. Skip the work, pay the architect.**

> ### "My time is money. My product is free."
>
> *The core philosophy of this repository.*

The purpose of this repository is that **you build it yourself**. The blueprint is free so that you can learn, put in the reps and produce the product on your own. That is the goal, and nothing
here is withheld to force a sale.

The **Industrial Build** exists for those who choose not to do that work. It is a **service**, and its price is **the master architect's fee**.

### What the $10,000 is, and what it is not

It pays for **my time, my engineering services and my custom architecture, packaged as a turnkey setup**: designed, wired, verified and installed on hardware you control.
It is **not** a charge for raw files, and it is **not** a charge for third-party models or libraries. Those stay under their own licences and are never resold; the build is configured
for components you are licensed to use for your purpose.

| | **DIY: this repository** | **Industrial Build** |
|---|---|---|
| Price | Free (CC BY 4.0) | **$10,000, one time, per licence**: an engineering-services fee |
| You receive | The framework, the empty skeletons, the specification, the assignment | The reference implementation, delivered turnkey: engines, bridge wiring, guardian, dashboard |
| Who builds it | **You**, with your own local AI | **Delivered built** and installed on hardware you control |
| Contract | None | **Mandatory digital licence and confidentiality agreement** |
| Support | None | Optional **$1,000 per month** retainer |
| Built for | Builders who want the skill and the product | Businesses that want the result without the build |

### Who it is for

Businesses and serious operators who would rather pay for the architect than spend the time to build, and who can sign a business agreement. **If you want to learn it, build it: the free path is
the real thing.** The Industrial Build is sold to **businesses only**.

### Mandatory digital contract

**Nothing is delivered before the agreement is signed.** One document carries both the software licence and the confidentiality terms, executed digitally by an **authorised signatory** of the
purchasing business, with the signatory's name, title and legal entity recorded. The signed agreement is the only source of binding terms; this page is a summary of it, not a substitute for it.
Terms change only by written addendum.

### Single-user licence

One licence covers **one named user** operating **one installation** on hardware the licensee controls. It is **non-transferable and non-sublicensable**. Additional users, installations or
sites each require a further licence, by addendum. The licence is **perpetual for the delivered version**: it keeps working if you never buy support.

### Anti-redistribution and confidentiality

No copying beyond internal backups, no resale, no sublicensing, no sharing with third parties, no hosting it as a service for others, no publishing or disclosing it or its materials, no
removing notices, and no using it to build a competing product for distribution. **Every delivery is individually identified**, and the agreement grants **audit rights**: a leak is traceable
to its source. Confidentiality obligations survive termination.

### Tiered consequences

| Tier | Breach | Consequence |
|---|---|---|
| 1 | Use beyond the licensed scope (more users, installations or sites) | Billed at the then-current licence price for the excess, from the date it began, and brought into compliance |
| 2 | Disclosure of confidential material, or breach of the confidentiality terms | Licence termination, return and destruction of all copies, injunctive relief, and damages including enforcement costs |
| 3 | Redistribution, resale, sublicensing or publication of the build | Everything in tier 2, plus liquidated damages as defined in the agreement |

Amounts and mechanics are set out in the agreement alone. They are designed to be proportionate and enforceable, not decorative.

### Support retainer

**$1,000 per month, optional.** It buys updates and security fixes for the delivered build, direct engineering help within a defined scope, and response targets that are written into the
agreement. Remote sessions happen only when you start them and only as long as you allow. **The retainer is never a runtime dependency**: if it stops, the system keeps running; you lose
updates and support, not the build.

### Third-party components

Open and third-party components keep their own licences and are delivered with their notices. They are not sold, not relicensed and not covered by the Industrial Build agreement.

### Inquiries

Contact the repository owner through their GitHub profile. State your business, your intended use and the number of users. This section is a summary of an offering, not an offer capable of
acceptance, and not legal advice.
