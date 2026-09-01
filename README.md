# Hermes Agent Grounding Skill

A truth protocol for LLM agents: **when is an agent allowed to claim something?**

The rule this skill exists for: **a tool succeeding is not an effect in the world.**
Code that ran without error is not a file on disk. A command sent is not a device
switched on. Proof is always a *separate read after the action*, with a different
tool than the one that performed it.

## What is in it

- **Six classes of claim** — world state, your own action, produced artifact, someone
  else's content, memory and the past, your own capabilities. Each class has one
  evidence obligation and one exact sentence to say when the evidence is missing.
- **Three gates** — before you start, while you claim, before you send.
- **The unit of proof is the detail, not the sentence.** An adjective next to someone's
  name, a number, a date, a clause tacked onto a true main clause — each is a separate
  claim. A sentence can be true at its core and false in its ornament, and then it is false.

## Why it is written this way

It replaces a 13 kB list of past incidents that still failed to prevent the next one.
Rules generalise; incident lists do not. New failures are not appended here — they either
fit an existing class or prove a class is described wrongly.

## Install

Copy into your Hermes skills directory:

```bash
git clone https://github.com/SebMaliszewski/hermes-agent-grounding-skill.git \
  ~/.hermes/skills/patrycja-grounding-protocol
```

The skill is a plain Markdown card. It works with any agent that can load skill files —
nothing in it is Hermes-specific, and it modifies no engine code.

## Note

This protocol does not block or regenerate anything. It is a card the model applies to
itself, not a guard that polices it. Keyword-based detection of unproven claims was
deliberately rejected: a false positive ruins an emotional conversation, and any list of
phrases will always miss the next word.

Written in Polish. MIT licensed.
