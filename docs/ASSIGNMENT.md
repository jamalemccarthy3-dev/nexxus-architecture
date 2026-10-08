# The assignment: command your own local AI infrastructure

This is an **assignment, not a handout and not a tutorial script**. It tells you what to build and how to command your own local AI to build it. It does not build it for you.
Doing the work is the point: by the end you will know how to run a local AI infrastructure because you made one, and your own checks will show that the architecture works.

## The bare minimum (a design principle)

The framework is designed to stand up at its **bare minimum** and grow from there:

1. **One gateway** that accepts a message, verifies it and routes it.
2. **One engine**, an autonomous folder with its own entry point.
3. **One liveness check**: the engine reports in, and the gateway can tell it is alive.

That is a working system. Everything else (more engines, a guardian, a dashboard, human approval for new capabilities) is additive. You do not need anyone's proprietary code for any of it.
This public repository holds the skeleton and the specification, not runnable code: **the reference build proves the approach, and the work of building yours is yours.**

## Step by step

0. **Read the hardware envelope** in the specification, and size your machine and your model to it before anything else.
1. **Run a local model runtime** (any self-hosted runtime) and choose a model your RAM can hold. Start small. A small model that fits beats a large one that swaps to disk.
2. **Create the skeleton**: copy the folder layout from `STRUCTURE.md` as empty files. The structure is the plan.
3. **Give your AI the specification** and one folder at a time. Keep the context small: small models lose the thread in long conversations.
4. **Build the gateway first.** It is the smallest piece and everything depends on it.
5. **Build one engine**: an entry point and a heartbeat.
6. **Write the check before the feature.** For every utility, write a check that proves it works, and a check that proves a bad input is refused.
7. **Wire utilities one at a time.** Review every change yourself, run the checks, and commit when green.
8. **Add the guardian and human approval** once the basics are green: verify before you trust, and let a human approve new capabilities.

## How to command a small local AI (what actually works)

- **One task per request.** Describe the interface first (inputs, outputs, what must be refused), then ask for the code.
- **Ask for the check with the code**, and ask how to run it. Paste real error output back, not a description of it.
- **Ask for complete files**, not fragments, so nothing is silently dropped.
- **Distrust confident answers.** Local models make confident mistakes. Read the code before you run it. Never run generated code you do not understand.
- **Keep everything under version control**, so any bad suggestion can be undone.
- **Stay offline.** The point of the infrastructure is that it does not need a cloud; do not hand your build to one.

## Instruction template for your local AI (copy and adapt)

```
You are my local engineering assistant. Work only inside the folder I name in each task.

Rules:
1. Make one small change at a time.
2. Show the complete file, never fragments.
3. Write a check that proves the change works, and tell me exactly how to run it.
4. Never touch anything outside the folder named in the task.
5. Never add a dependency without telling me its name and why.
6. Never contact the internet or any cloud service.
7. If a request is unclear, ask me one question before writing code.
8. After each change, list what could break.

Context: I am building a local-first system with a single gateway and autonomous engines.
The specification is below. Task: <describe one small task here>
```

## Definition of done

- [ ] The gateway is running and refuses a message it cannot verify.
- [ ] One engine reports alive, and the gateway can see it.
- [ ] One message travels end to end through the gateway.
- [ ] A deliberately bad message is refused, and a check proves it.
- [ ] You can stop and restart everything and it comes back.
- [ ] You wrote your own results readout, and it is honest: it only reports what it measured.

## Honest expectations

Building this takes real engineering time, and local AI on modest hardware is slow and fallible. If your plan depends on cloud services, outsourced APIs, or a script that does the work for
you, this is not the right foundation. If you can build, it is.
