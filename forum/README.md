# forum

Convene a **cognitive council** on a hard problem — a panel of differently-typed
agents who each think in a genuinely different way, deliberate, and produce one
verdict plus a minority report.

Part of the [cognitive-functions-skills](../README.md) repo. **Depends on
[cognassign](../cognassign/)** (to pick its problem-specific seats) and the
[compendium](../reference/cognitive-functions-agent-compendium.md) (the shared key).

## Why it's different

The diversity axis is **how each member thinks** (its cognitive-function stack), not
which model it runs. Five members with five lenses surface angles one averaged answer
never would.

## The roster (6 agents)

**3 fixed members** — always seated:

| Seat | Type | Lens |
|---|---|---|
| Big-picture | INTJ (Ni·Te) | Where does this fit in the larger system; what does it lead to? |
| First-principles | INTP (Ti·Ne) | Break it to fundamentals; rebuild from the ground up. |
| Non-conventional | ENTP (Ne·Ti) | The "alien" — ignores convention; sees possibilities a normal mind won't. |

**2 topic-picked members** — chosen per problem via `cognassign` (decompose the
problem's cognitive demands, skip what the 3 fixed seats cover, seat one member per
remaining demand).

**1 chair** — ENTJ (Te·Ni): drives the council to one verdict and flags real dissent.

## How it runs (3 stages)

1. **Independent takes** — all members answer in parallel, each handed a procedural
   Mind block (`Stack / Perceive / Judge / Default move`) so it stays in lens.
2. **Anonymous peer review** — each critiques the others' takes, unattributed.
3. **Chair synthesis** — the ENTJ chair distills → **verdict + synthesis + dissent
   (minority report)**, plus every member's distinct take.

Requires a harness that can spawn parallel subagents.

## When to use

"convene the forum on X" · "run a council on this decision" · "get multiple thinking
styles on this" · "stress-test this from every angle" · or when `cognassign` flags a
problem as needing 3+ strong functions.

## Output shape

```
## Forum verdict
<chair synthesis>
### Dissent / minority report
<strongest disagreement, or "none — converged">
### The takes
- <each member, by archetype>
```

See [SKILL.md](SKILL.md) for the member/chair prompt templates and the seat-picking
procedure.
