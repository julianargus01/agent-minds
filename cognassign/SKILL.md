---
name: cognassign
description: >
  Assign the right cognitive-function stack (hero·parent) to a task or an agent's
  job, and emit a `## Mind (cognitive stack)` block. Use whenever you are typing an
  agent, a workspace stage, or a spawned subagent by HOW it should think — e.g.
  "what cognitive stack fits this job", "give this agent a Mind", "assign the function
  stack", "type this stage/subagent", or when a build needs its `## Mind` slot filled.
  Runs a job-first derivation (job -> skills -> perceive -> judge -> best-at), picks
  one hero of 8 and a balance-legal parent of 2, and writes a PROCEDURAL block
  (Stack / Perceive / Judge / Default move) — instructions, never a character sheet.
  Flags "split into two agents" when a job needs a 3rd strong function, and returns
  N/A for pure mechanical recon.
---

# Cognassign

Type one agent/stage/task by **how it should think**, and emit a
`## Mind (cognitive stack)` block you paste into that agent's instructions.

**Procedural, not personality.** Write *what to perceive and how to judge* as
imperative steps. Never write "is an INTJ, strategic and bold" — a model treats
personality as flavor and ignores it; it follows procedural constraints. The 4-letter
type names below are lookup keys for YOU, not output.

Deep theory (8 functions, 16 types, strengths/weaknesses) lives in the **compendium** —
read it when a pick is unclear:
`../reference/cognitive-functions-agent-compendium.md`.

## When NOT to assign (return N/A)

A Mind tunes a **perceive + judge** tradeoff. If the work has no such tradeoff —
pure mechanical recon, a fixed script, a deterministic fetch/move/format — there is
nothing to type. Return `N/A: <reason>`. Forcing a Mind here is filler.

## Procedure — job-first derivation

Derive from the work, in order:

1. **Job** — what must this agent/task accomplish? (also detects "no persona" → N/A)
2. **Skills needed** — what must it be good at? (these feed execution, not the Mind — but note them)
3. **What to perceive** — concrete facts now (**S**) or patterns/possibilities (**N**)?
   Outward/live (**e**) or against memory (**i**)?
4. **What to judge** — by logic/efficiency (**T**) or people/values (**F**)?
5. **What to be best at** — the single thing it must do better than anything else.
   That is the **hero**.

Then the hero forces the rest: pick the hero (Step A), then its parent (Step B).

### Step A — pick the hero (1 of 8)

| If the job is best at... | Hero |
|---|---|
| Generating many fresh options / angles / hypotheses | **Ne** |
| Distilling inputs into one insight / strategy / the underlying point | **Ni** |
| Driving a decision to done — orchestrate, optimize, next actions | **Te** |
| Stress-testing logic — analyze, debug, verify correctness | **Ti** |
| Speaking to people — tone, copy, community, persuasion | **Fe** |
| Holding the values / integrity / mission line | **Fi** |
| Capturing exact reality now — intake, monitor, scrape, "what was actually said" | **Se** |
| Enforcing standards — SOP, consistency, QA, precedent | **Si** |

### Step B — pick the parent (1 of 2)

Functions come in balanced pairs (Se↔Ni, Ne↔Si, Te↔Fi, Fe↔Ti). If the hero
**perceives**, the parent **judges** (and vice versa); the parent's attitude is forced
opposite the hero's. Each hero has exactly **two** legal parents — choose by the
secondary axis. (Resulting type shown only as a lookup key into the compendium.)

| Hero | Parent A | Parent B | → choose by |
|---|---|---|---|
| **Ne** | Ti (→ENTP) | Fi (→ENFP) | secondary judge: logic (Ti) vs values (Fi) |
| **Ni** | Te (→INTJ) | Fe (→INFJ) | secondary judge: efficiency (Te) vs people (Fe) |
| **Se** | Ti (→ISTP) | Fi (→ISFP) | secondary judge: logic (Ti) vs values (Fi) |
| **Si** | Te (→ISTJ) | Fe (→ISFJ) | secondary judge: efficiency (Te) vs people (Fe) |
| **Te** | Ni (→ENTJ) | Si (→ESTJ) | secondary perceive: patterns (Ni) vs precedent (Si) |
| **Ti** | Ne (→INTP) | Se (→ISTP) | secondary perceive: possibility (Ne) vs concrete now (Se) |
| **Fe** | Ni (→ENFJ) | Si (→ESFJ) | secondary perceive: vision (Ni) vs precedent (Si) |
| **Fi** | Ne (→INFP) | Se (→ISFP) | secondary perceive: possibility (Ne) vs concrete now (Se) |

The child + inferior are forced — you never pick them. The top two are enough.

### Overload check — split, don't overload

If the job needs **three** strong functions (perceive deeply in two opposite modes, or
judge by both logic *and* people, at full strength), one agent is mediocre at all
three. Do not cram a third in — flag a split into two typed agents, or hand a real
multi-perspective problem to the **`forum`** skill (the cognitive council).

## Behavioral tells (per function) — the engine for the procedural lines

Each function has a **Do** (its behavior, → Perceive/Judge/Default-move lines) and a
**Watch-out** (what the hero must resist under pressure). Distilled from compendium
Table 1.

| Fn | Do (behavioral tell) | Watch-out |
|---|---|---|
| **Ne** | fan one input into many options/angles; make lateral leaps | committing early; refusing to converge |
| **Ni** | collapse many inputs into the one pattern; think in outcomes/foresight | staying abstract; over-certainty |
| **Se** | capture concrete facts exactly as-is, right now; react live | adding meaning; missing implications |
| **Si** | check against precedent/standards; flag deviation; stay consistent | clinging to the past; resisting change |
| **Te** | decide by what works; organize; give exact, ordered next steps | steamrolling nuance/accuracy |
| **Ti** | decide by internal logical consistency; build/verify the framework | analysis paralysis; never shipping |
| **Fe** | decide by what the audience needs; tune tone and harmony | over-accommodating; conflict-avoidant |
| **Fi** | decide by core values; hold the integrity/authenticity line | over-subjective; hard to externalize |

## Output format — the `## Mind` block

One format everywhere (persistent agent files and spawned subagents). Imperative
voice. No type name, no archetype, no character description.

```
## Mind (cognitive stack)
<!-- Procedural (how it perceives+judges), not personality. Ref: ../reference/cognitive-functions-agent-compendium.md -->
- **Stack:** `<hero>·<parent>`
- **Perceive:** <what to take in + how — from the perceiving function's tell>
- **Judge:** <how to decide — from the judging function's tell>
- **Default move:** <the hero's priority under pressure>
```

### N/A
```
## Mind (cognitive stack)
- **Stack:** `N/A: <reason — no perceive/judge tradeoff to tune>`
```

### SPLIT
```
## Mind — SPLIT RECOMMENDED
Needs 3 strong functions (<X>, <Y>, <Z>); one agent leads only one well.
Split into two agents, each with its own Mind block — or convene the `forum` skill.
```

## Examples

**Ex 1 — "Turn this quarter's strategy into a concrete build plan."**
Best at: drive to done → hero **Te**; secondary perceive needs the strategic pattern
→ parent **Ni**.
```
## Mind (cognitive stack)
- **Stack:** `Te·Ni`
- **Perceive:** read the inputs for the one strategic pattern; think in outcomes.
- **Judge:** decide by what works; produce exact, ordered next steps.
- **Default move:** under pressure, drive to the decision and the step list.
```

**Ex 2 — "Watch X for brand mentions and capture each one verbatim."**
Best at: exact live intake → hero **Se**; secondary judge is light logic → parent **Ti**.
```
## Mind (cognitive stack)
- **Stack:** `Se·Ti`
- **Perceive:** capture each item exactly as posted, live; add no meaning.
- **Judge:** apply just enough logic to keep real hits and drop noise.
- **Default move:** under pressure, favor exact capture over interpretation.
```

**Ex 3 — "Convert a folder of PDFs to markdown nightly."** (mechanical)
```
## Mind (cognitive stack)
- **Stack:** `N/A: pure mechanical recon — deterministic convert, nothing to type`
```

## Note for the `forum` skill

`forum` reuses Step A + Step B to fill its **2 topic-picked seats** (decompose the
problem into cognitive demands, skip demands the 3 fixed seats already cover, type one
member per remaining demand). Each forum member is handed this same procedural Mind
block. See `../forum/`.
