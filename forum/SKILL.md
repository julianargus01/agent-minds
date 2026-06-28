---
name: forum
description: >
  Convene a cognitive-function council on a hard problem — a panel of MBTI-typed
  members who each think in a genuinely different way, deliberate in parallel,
  peer-review anonymously, then a chair synthesizes a verdict with a minority report.
  Use when a question is big, ambiguous, high-stakes, or benefits from clashing
  perspectives — "convene the forum", "run a council on this", "get multiple thinking
  styles on this decision", "stress-test this from every angle", or when the
  `cognassign` skill flags a problem as needing 3+ strong functions (split). Seats 3
  fixed members (big-picture, first-principles, non-conventional) + 2 picked for the
  topic + a chair. Each member is built from a cognitive-function stack, with the
  compendium as the shared reference key.
---

# Forum — the Cognitive Council

Six agents think on one problem, each from a different cognitive-function stack, so
you get real perspective diversity instead of one averaged answer. The diversity axis
is **how each member thinks** (its function stack), not which model it runs.

Shared reference key for every member:
`../reference/cognitive-functions-agent-compendium.md`.

## The roster (6 agents)

**3 fixed members** — always seated:

| Seat | Type | Stack | Lens |
|---|---|---|---|
| **Big-picture** | INTJ | Ni·Te·Fi·Se | Zooms out — where does this fit in the larger system, and what does it lead to? |
| **First-principles** | INTP | Ti·Ne·Si·Fe | Breaks the question to fundamentals and rebuilds it from the ground up. |
| **Non-conventional** | ENTP | Ne·Ti·Fe·Si | The alien — ignores our conventions/assumptions; sees possibilities and connections a normal mind won't. |

**2 topic-picked members** — chosen per problem (see below).

**1 chair** — always:

| Seat | Type | Stack | Job |
|---|---|---|---|
| **Chair** | ENTJ | Te·Ni·Se·Fi | Drives the council to one verdict; synthesizes the takes and flags real dissent. (Mirror of the big-picture INTJ — INTJ *sees*, ENTJ *decides*.) |

## Picking the 2 topic-picked seats

Use the **`cognassign`** procedure (Step A + Step B):

1. Decompose the problem into its cognitive **demands** — which of the 8 functions
   does this specific question genuinely need? (e.g. a launch call needs Se = real
   market facts, Fe = audience reaction, Fi = vision-fit; a debugging post-mortem
   needs Si = precedent, Te = fix-and-ship.)
2. **Skip demands the 3 fixed seats already cover** — Ni (big-picture), Ti
   (first-principles), Ne (non-conventional).
3. From what's left, take the **2 strongest** demands and type one member each
   (hero·parent → full MBTI type from the compendium tables).
4. If fewer than 2 real extra demands exist, this may not need a council — consider
   just using `cognassign` to type one agent. If far more than 2, the problem is
   too big — split the problem, don't add seats.

State the 2 picks + why before running, so the lineup is auditable.

## Mechanism — 3 stages

Run members in parallel via your agent/subagent tool. Suggested models: a fast capable
model for the 5 members, your strongest model for the chair. Hand every member full
context: the problem **plus its procedural Mind block** from `cognassign`
(Stack / Perceive / Judge / Default move) — instructions, not a character sheet. A
member never reads the compendium mid-run; the procedural lines carry the behavior
inline. Build each block with `cognassign`'s "Behavioral tells" table. (The seat names
below are organizational labels for you; the agent's instructions are the procedural
lines, not "be an INTJ.")

### Stage 1 — independent takes (parallel)
Dispatch all **5 members** in one batch. Each answers alone.

**Member prompt template:**
```
You reason through ONE cognitive lens. Follow this Mind — let the perceive step
gather and the judge step decide. Do not try to be balanced or cover other angles;
that is the council's job, not yours.

## Mind (cognitive stack)
- Stack: <hero>·<parent>
- Perceive: <perceiving function's Do — imperative>.
- Judge: <judging function's Do — imperative>.
- Default move: <hero's priority under pressure>.

Answer this question entirely by running that Mind. Be specific.

Question: <query + any context>
```
Collect, then label takes by archetype (Big-picture / First-principles / etc.).

### Stage 2 — anonymous peer review (parallel)
Dispatch the same members again; each sees the **other** takes, anonymized
(Take A / B / …), and critiques: what's sharp, what's blind, what's wrong. Keep it
short and pointed. (Anonymity keeps it about the idea, not the persona.)

### Stage 3 — chair synthesis
One **ENTJ** chair (strongest model) receives all takes + all reviews and produces the
output. The chair drives to a decision; it does not just average.

**Chair prompt template:**
```
You are the ENTJ (Te·Ni) chair of a cognitive council. You have <N> independent
takes on a question, each from a distinct cognitive lens, plus peer reviews.

Question: <query>
Takes: <labeled takes>
Reviews: <reviews>

Produce:
1. SYNTHESIS — the single best answer/recommendation. Drive to a decision; apply
   valid criticism; correct errors. Don't fence-sit.
2. DISSENT — if any member strongly disagrees with the synthesis on a point that
   matters, state that minority report plainly and why it might be right.
Be decisive but honest about uncertainty.
```

## Output to the user

```
## Forum verdict

<chair synthesis>

### Dissent / minority report
<the strongest disagreement, or "none — the council converged">

---
### The takes
- **Big-picture (INTJ):** <take>
- **First-principles (INTP):** <take>
- **Non-conventional (ENTP):** <take>
- **<topic seat 1> (<TYPE>):** <take>
- **<topic seat 2> (<TYPE>):** <take>

*Lineup: 3 fixed + 2 topic-picked (<why>) + ENTJ chair.*
```

## Notes
- Keep the question crisp. If the user gives only `/forum` with no question, ask
  "What's the question for the forum?"
- A member's value is its *bias* — do not sand the lenses down to sound reasonable.
  The non-conventional seat especially should feel a little alien.
- This is the home for `cognassign`'s SPLIT flag: when one job needs many strong
  functions, convene them here instead of overloading one agent.
- Requires a harness that can spawn parallel subagents.
