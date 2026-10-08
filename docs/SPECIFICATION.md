# Autonomous Automation AI Infrastructure and Orchestrator: architecture specification

**NEXXUS**, specified.

This is the public specification of the **layout and the limits** of a local-first, SaaS-free multi-engine system. It describes the design. It contains no implementation.

## Distribution model: infrastructure, not handouts

**This specification describes the sovereign orchestration framework and its empty utility skeletons. It does not include proprietary, plug-and-play source code.**

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

## 1. Overview

| In my words | The formal technical equivalent |
|---|---|
| **Autonomous Automation** | **Agentic workflow automation** with bounded autonomy and human-in-the-loop governance |
| **AI Infrastructure** | **Self-hosted, local-first AI infrastructure**: a local model-serving runtime plus a modular multi-engine service platform on a single node |
| **Orchestrator** | **Orchestration layer / control plane**: hub-and-spoke service orchestration through a single gateway, with a policy-enforcement (guardian) layer |
| **The whole system** | **A self-hosted, local-first, multi-engine AI orchestration platform** (SaaS-free, zero-cloud local orchestration) |

In detail: a **modular multi-engine architecture** with **zero-cloud local orchestration**, designed for **personal sovereignty** (**data and compute sovereignty, on-prem / edge**) and
**high-level autonomous development** on **one machine**. 22 standalone engines connect through a single gateway (**hub-and-spoke**); a private core orchestrates;
a guardian verifies what may pass or run; a dashboard presents it all.

## 2. Components

| Component | Role | Technical term |
|---|---|---|
| Engines | Self-contained units of capability, one folder each | Loosely coupled, process-isolated service modules |
| Bridge | The one door every cross-boundary message uses | Gateway / integration hub (hub-and-spoke) |
| Core | Decides, plans and delegates | Orchestrator / control plane |
| Guardian | Verifies messages, tracks drift, decides what may run | Message-integrity and policy enforcement layer |
| Dashboard | The user interface | Presentation layer |

## 3. Integration path (for anyone building their own)

1. **Size the machine.** Decide your hardware envelope first (section 4). Everything else follows from it.
2. **Run a local model runtime.** Any self-hosted runtime works. Choose models your RAM can hold.
3. **Make each engine an autonomous folder** with its own entry point. Nothing outside an engine should need to know how it works inside.
4. **Put one gateway in front.** All cross-boundary traffic goes through it; engines never call each other. You gain a single place to observe, guard and change the system.
5. **Verify before you trust.** Treat every message and every new capability as untrusted until it has been verified or explicitly approved by a human (**human-in-the-loop governance**).
6. **Keep the interface self-contained.** Bundle its assets so that it loads nothing from the internet at startup.
7. **Prove it.** Write automated checks for liveness *and* behaviour. A component that is "up" has proved only that it is up.

You write your own engines and your own wiring, by working with your own local AI. The proprietary wiring of this system is private and is not part of this specification.
The guide for doing that is [`ASSIGNMENT.md`](ASSIGNMENT.md).

## 4. Capacity and limits: the hardware envelope

**Contract.** This design is a **local, sovereign, zero-subscription powerhouse** that runs on **single-machine physics**. The CPU, the RAM and, where present, the GPU and its memory set
the ceiling. It behaves like an "unlimited" plan: very high capability, but past a threshold of **heavy concurrent local generation** you hit the hardware wall.
It is built for **absolute personal sovereignty and high-level autonomous development**, not for **infinite multi-node cloud scaling out of the box**.

**Reference system.** A dual-core desktop CPU in the 3 GHz class, about 8 GB of RAM, integrated graphics, no discrete GPU, a mainstream desktop operating system, models running on the CPU.
The complete system, with all engines live, runs on it. Treat that as the floor.

**Concurrency is bounded by design**, so that the machine degrades by queuing instead of failing:

| Resource | Behaviour |
|---|---|
| Model generation while building | One call at a time; others wait their turn |
| Background jobs | A small worker pool; the rest queue |
| Sandboxed capability runs | Two at a time, with per-call time, memory and output limits, and a per-minute rate limit |
| Model memory | Models stay loaded for a while after use; switching modes swaps models, which costs time on a CPU |

**What the wall looks like.** Chat alongside one build works. Many builds, a large model and many busy engines at once will queue, slow down, or exhaust RAM and start swapping to disk.
Latency grows long before anything fails outright.

**Raising the ceiling (vertical scaling).** More RAM, a fast SSD, a discrete GPU with enough video memory, a larger model, larger worker pools. Each is a change on the same machine.

**Not provided (horizontal scaling).** No cluster scheduler, no shared state across machines, no cross-machine authentication, no failover. Running across several machines is a
different architecture that you would design and build. A single machine is also a **single point of failure**: back it up.

"Zero cost" means no subscription or licence fee. The hardware and the electricity are yours.

## 5. Zero-cloud, and its exact boundary

Nothing in the system requires a cloud service to run, and the dashboard **loads nothing from the internet**: its 3D library and visuals are bundled with it.
A small number of features reach the internet **only when you start them**, and every one of them can be left off:

1. Fetching an open-source capability from a public code host, after which a human approves it.
2. Web search and recon: the dashboard search box, the chat search command, and a scrape pipeline against a target you name.
3. Remote access through a private network tunnel, if you set one up.
4. Installing the packages a capability needs: you run the command yourself.

## 6. What is and is not provided

| Provided, under CC BY 4.0 | Not provided |
|---|---|
| This specification, the layout, the boundaries and the reasoning | Engine source code, except under the separate Industrial Build agreement |
| The public facade: every folder and file name as a map | The proprietary internal wiring |
| | Configuration, data and anything private |

## 7. Telemetry and proof

The reference build publishes proof-of-life receipts (see the README): live component counts, verified-message counts and master-suite results, generated from real runs, results only.
They describe the **reference build** and are evidence that the architecture runs locally with no cloud. They are not a claim that this repository, which holds only skeletons, can be run as is.

## 8. Acknowledgments and third-party credit

**Google and Gemini: the core architectural partner.** A tribute to the free intelligence layer that helped collect the thoughts, structure the engine parameters and co-architect this
system from the ground up. Gemini was a **design-time partner**: nothing in the running system depends on it.

**Hugging Face**, the open hub that makes models, datasets and tooling accessible to everyone. **Llama**, the open-weight models from Meta that make serious local inference possible on ordinary hardware.

Together they are the trifecta of the **open and accessible stack** that made sovereign, local-first infrastructure possible.
Product names and marks belong to their owners; their mention here is gratitude, not endorsement by them.

The dashboard's 3D view uses **Babylon.js**, licensed under the Apache License 2.0, bundled with the private dashboard.
