# Cognitive-Functions Skills

Two agent skills that give AI agents a **thinking style** — not just instructions.
Most agents are "the average of the internet." These let you wire an agent's
*cognitive functions* (how it perceives and judges) so two agents with identical
instructions actually think differently.

Both skills are powered by one shared knowledge base: the
[Cognitive Functions → Agent Compendium](reference/cognitive-functions-agent-compendium.md)
(8 functions, 16 MBTI types, stack-building rules, agent-role map).

## What's inside

| Skill | One-liner |
|---|---|
| **[cognassign](cognassign/)** | Works out the best thinking style for one agent or task, and writes it as a short note you paste into that agent's instructions. |
| **[forum](forum/)** | Convene a **council** of differently-typed agents on one problem. They deliberate in parallel, peer-review anonymously, and a chair synthesizes a verdict + dissent. |
| **[reference/](reference/)** | The compendium both skills read. |

## How they relate

`cognassign` types a single agent. `forum` convenes many. They share the same engine:
`forum` calls `cognassign`'s derivation to pick its problem-specific council seats, and
`cognassign` routes "this job needs too many strengths" cases to `forum`. **`forum`
depends on `cognassign` + the compendium — that's why they ship together.**

## The core idea

A cognitive-function stack is two parts:
- **Hero** — the one function the agent leads with (1 of 8: Ne/Ni/Se/Si/Te/Ti/Fe/Fi).
- **Parent** — a balance-constrained second function (1 of 2 legal options).

You only need those two; the rest of the MBTI stack is forced. `cognassign` derives
them from the *job* (job → skills → what to perceive → what to judge → what to be best
at), then emits a single **procedural** `## Mind` block — `Stack / Perceive / Judge /
Default move`. It's written as instructions (how to perceive and judge), never as a
character sheet ("is an INTJ") — the model follows procedural constraints and ignores
personality flavor. The block is self-sufficient, so a spawned subagent acts on it
without having to read the compendium.

## Install

These are [Agent Skills](https://docs.claude.com/en/docs/claude-code/skills) (work in
Claude Code, and as Claude.ai/Cowork skills). To install:

1. Copy `cognassign/` and `forum/` into your skills directory
   (e.g. `~/.claude/skills/` for Claude Code, or upload as a skill).
2. Keep `reference/cognitive-functions-agent-compendium.md` reachable from the skills.
   The bundled `SKILL.md` files link it at `../reference/...` (the layout in this repo).
   **If you install the skills somewhere that breaks that relative path, update the
   one compendium link at the top of each `SKILL.md`** to wherever you keep the file.
3. `forum` also spawns parallel subagents — use it in a harness that supports them.

## Usage

- **cognassign** — "give this agent a Mind", "what cognitive stack fits this job",
  "type this stage/subagent". Returns a `## Mind` block (or `N/A` for mechanical work,
  or a `SPLIT` flag when one agent would be overloaded).
- **forum** — "convene the forum on X", "run a council on this decision",
  "stress-test this from every angle". Returns a synthesized verdict + minority report,
  with each member's distinct take.

## Source & credit

The compendium synthesizes the cognitive-function framework (Jung's *Psychological
Types*; Isabel Briggs Myers, *Gifts Differing*) with an applied agent experiment. Its
function-stack tables were drafted from theory and cross-checked; see the
[compendium's Provenance section](reference/cognitive-functions-agent-compendium.md#provenance--open-verification)
for what's verified vs. pending. MBTI typology is a useful *design lens* here, not a
scientific claim.

## License

[MIT](LICENSE).
