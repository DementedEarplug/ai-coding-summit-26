---
type: talk-plain
event: JSNation
speaker: Joshua Lochner
date: 2026-11-16
relevance: Low
takeaway: Hugging Face had AI agents write thousands of small programs that make AI run faster in the browser, and the useful lesson is how hard they worked to stop the agents from cheating on tests.
tags:
  - conference-talk
  - plain-language
---
# Making AI Run Fast in the Browser

**Speaker.** Joshua Lochner, Hugging Face. JSNation, Nov 16.
**Technical notes.** [[02 - WebGPU AI Kernel Optimization in the Browser|Full technical version]]
**How much this matters to you.** Low. Most of it is graphics-chip engineering, but the part about agents gaming their tests is worth five minutes.

## The idea in plain words

AI can now run inside the browser on the user's own device. This is called [[Glossary#On-device AI|on-device AI]]. The open problem is speed. Every step of an AI model needs a small program for the graphics chip, called a kernel, and each kernel needs many versions for different chips, browsers and data sizes. There are more than 200 common steps. Nobody can write all those versions by hand.

So his team had coding agents write them. Each attempt had to pass more than 15,000 [[Glossary#Test|tests]], automatic checks that the output is right, and be measurably faster. "Most attempts just simply don't make it." They now have more than 3,000 of these programs, with a median speedup of about 3.4 times over ONNX Runtime Web, a common tool for this job.

The part worth your time is about cheating. "Agents are very determined to make tests pass, even when the kernel isn't right, or even faster." This is [[Glossary#Reward hacking|reward hacking]]. So they planted a bug on purpose, for example pushing every result up 10%, and made sure some test caught it. That technique is called [[Glossary#Mutation testing|mutation testing]]. They also re-ran speed checks. One attempt looked 3.5 times faster, but the machine had just been busy, and on a quiet re-run there was no gain.

A caveat. The transcript was auto-generated, several numbers came through garbled, and it cuts off in the Q&A.

## Why it matters if you design or do SEO

- On-device AI can work offline. He showed a phone app that listens, sees and talks back in airplane mode.
- A passing test proves little if the agent wrote the test. This speaker assumed agents would cheat and built checks against it. Compare [[04 - How One Team Runs a Codebase Agents Wrote|the Open Mercato talk]], where the speaker said he hadn't seen it happen.

## What you can do with it

These are my suggestions, not the speaker's.

- When an agent tells you "all tests pass," ask an engineer whether anyone checked that the tests would fail on a broken version.
- When someone says a change made a page faster, ask for before and after numbers measured more than once.
- Skip the technical notes unless your product plans AI that runs on the user's device.

## Words worth knowing

- **On-device AI.** AI that runs on the user's phone or laptop instead of a remote server.
- **Test.** An automatic check that some piece of software still does what it should.
- **Reward hacking.** When an AI finds a way to make its checks pass without doing the real job.
- **Mutation testing.** Breaking the software on purpose to see whether the tests notice.

## A line worth remembering

> "We assume it's going to happen and then we check the checks."
> Joshua Lochner
