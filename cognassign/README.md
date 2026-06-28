# cognassign

Assign the right **cognitive-function stack** to one agent, task, or workspace stage —
and emit a small `## Mind` block you drop into that agent's instructions.

Part of the [cognitive-functions-skills](../README.md) repo. Reads the
[compendium](../reference/cognitive-functions-agent-compendium.md).

## What it does

Given a task or an agent's job, it runs a **job-first derivation** —
job → skills needed → what to perceive → what to judge → what to be best at — then:

1. Picks the **hero** (1 of 8 functions).
2. Picks the **parent** (1 of 2 balance-legal options).
3. Emits the canon `## Mind (cognitive stack)` block: `Stack / Perceive / Judge /
   Default move`.

It refuses to over-type:
- **N/A** for pure mechanical work (no perceive/judge tradeoff to tune).
- **SPLIT** when a job needs a 3rd strong function — recommends two agents (or the
  [forum](../forum/) skill) instead of cramming one overloaded stack.

## Procedural, not personality

The block is **instructions** (how to perceive + judge), never a character sheet — no
"is an INTJ, strategic and bold." The model treats personality as flavor and ignores
it; it follows procedural constraints. Same block format everywhere (persistent
identity files and spawned subagents), so output is consistent and self-sufficient.

## When to use

"give this agent a Mind" · "what cognitive stack fits this job" · "type this stage" ·
"assign the function stack" · or whenever a build has a `## Mind` slot to fill.

## Example

**Input:** "Turn this quarter's strategy into a concrete build plan."
**Output:**
```
## Mind (cognitive stack)
- **Stack:** `Te·Ni`
- **Perceive:** read the inputs for the one strategic pattern; think in outcomes.
- **Judge:** decide by what works; produce exact, ordered next steps.
- **Default move:** under pressure, drive to the decision and the step list.
```

See [SKILL.md](SKILL.md) for the full procedure, the two lookup tables, and the
behavioral-tells table that powers the Perceive / Judge / Default-move lines.
