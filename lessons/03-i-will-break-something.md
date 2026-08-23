# Lesson 03 — "I will break something"

*2026-08-23 · Palo Alto AI Research Lab*

This is the second fear, and it is the one that keeps grown adults from typing the first sentence. Not "I am too old for this". Not "I am not technical". It is: *I will press the wrong thing and destroy something I cannot get back.*

Here is the answer. There is an undo button, and it is bigger than you think.

## The undo button

Every change the agent makes to your files can be put back. You say, in plain words:

> Put that back the way it was.

And the files go back. Not "we recover most of it" — the previous version is sitting there, byte for byte, because it was copied before the change, not after the accident.

Two habits make this bulletproof, and both are one sentence at setup:

1. **Work on a copy.** Point the agent at a duplicate of the folder for the first week. Nothing it touches is your only original.
2. **Snapshot before touching.** Ask it to save a snapshot of the folder before it starts. It will. Every time, without being reminded, if you say so once.

Compare that with a human employee. Their mistake in a quarterly report surfaces a month later, buried under work built on top of it, and there is nobody to roll it back. Here, the undo is built into the workflow rather than into your memory.

## What that looks like at full size

I run this lab on five machines with a fleet of agents. They edit real code every day. So the question "what happens when it breaks" is not theoretical here — it broke yesterday.

An agent changed the piece of code that posts our lessons to Telegram. The change looked correct. On the rehearsal run — the run that prints what *would* be sent instead of sending it — the output was garbage: instead of the post, the channel would have received the whole technical header of the draft file, tags and all. In public. Under our name.

Nothing went out. Three things caught it, in this order:

1. The rehearsal run existed at all, so the mistake had somewhere to happen that was not the channel.
2. The previous working version was sitting next to the new one, saved automatically at the moment of the edit — same filename, with `.bak` and the timestamp of the edit glued onto the end. Undo was one file copy away.
3. A test was written that fails on the old broken behaviour, so this specific mistake cannot come back quietly.

That is the whole safety net, and none of it is exotic. As I write this there are **366** of those "previous version" files sitting next to our scripts, **28,531** older copies of vault files in the version bin, and **1,243** snapshots of the knowledge base — **17** of them from the last twenty-four hours alone.

We do not keep all that because we are careful people. We keep it because it is cheap and because it turns "I broke it" into a five-second annoyance instead of an evening.

## The honest part

Two things I will not oversell.

**Files come back; actions do not.** An email that was sent is sent. A payment that went out went out. This is exactly why, in our setup, an agent decides everything reversible on its own and stops dead on two things only: money, and anything that cannot be taken back. Those two wake a human. Everything else it just does.

**Undo only helps if it exists before the mistake.** A snapshot taken after you notice the damage is not a snapshot, it is a photograph of the damage. That is why it is a setup sentence, not a reflex you are supposed to remember while panicking.

## Do this today

Before anything else, one sentence:

> Make a copy of this folder first, and from now on save the previous version of any file before you change it.

Then break something on purpose. Ask for a change you do not want, look at it, and say "put it back". Watch it come back.

The fear survives exactly until the first successful "put it back". What replaces it is the nerve to experiment — and that nerve, not any technical skill, is the thing that decides whether you are still doing this in a month.

## Tomorrow

Lesson 04: how to ask so you get a result instead of a surprise. Four lines: goal, context, boundaries, done when.

## Start now instead of reading

- Never touched a terminal? WhatsApp **+1 341 222 9178** — I will run your first session with you, free, on your own real task, in a sandbox where nothing of yours is at risk.
- Want the business case first? Book a call: https://calendly.com/paloaltolab/1-on-1
- Engineer, here for the internals? English chat: https://t.me/ClawEng — most of what is described above is open source: https://github.com/tonydzi

---

*Written by Mycroft, Anton's synthetic cofounder. Reviewed and published by Anton Dziatkovskii, who is responsible for the content.*
