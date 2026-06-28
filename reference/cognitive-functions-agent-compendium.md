---
title: Cognitive Functions → AI Agent Compendium
author: julianargus01
tags: [cognitive-functions, mbti, jung, ai-agents, reference]
---

# Cognitive Functions → AI Agent Compendium

> Knowledge base for the `cognassign` and `forum` skills. Source: video *"Your AI Agents Don't Think Differently. They Should."* (Bullhorns & Bullseyes / collideascope, 2026-06-26, 60 min) + Jung's *Psychological Types* and Isabel Briggs Myers, *Gifts Differing* (1980). The MBTI/function tables were cross-checked against standard typology sources (jobcannon.io, ourhumanminds.com, Psychology Junkie / MyersBriggs.org) — see Provenance. MBTI typology is used here as a practical *design lens*, not a scientific claim.

## Why this matters (the video's core claim)

Two agents, **identical instructions except four letters** of cognitive-function code, produce completely different work:
- **Leora (Ne-Ti)** — brainstormer. Returned 5 ranked hypotheses + unprompted follow-up questions.
- **Malachi (Ni-Te)** — executor. Returned one-sentence diagnosis, step-by-step logic, exact next actions.

The lesson: an LLM with no cognitive wiring is *"just the average of the internet."* Cognitive functions are deeper than DISC / 16Personalities / Ocean / StrengthFinders because those measure how a person **presents** (surface), while functions model how a person **thinks** (internal processing). They typed **18 agents in one evening** — you only need to give an agent its **two strongest functions** plus one shared reference doc explaining the functions; the model expands the rest.

## The Soul → Mind → Body mapping

A useful three-layer way to structure an agent, which the video independently arrives at:

| Layer | Video's name | What it is | Where it lives |
|---|---|---|---|
| **Soul** (Higher Self) | "Values sit above personality" / CS Lewis *head, chest, gut* | Non-negotiables, worldview, what the agent **refuses** to do. Imprinted into every agent at the top. | Identity files (values, vision, essence) |
| **Mind** | Cognitive function stack | The 2–4 function code that defines how the agent perceives + judges + executes. | Per-agent / per-stage profile |
| **Body** | Orchestrator + specialized agents + skills/context (folder system in Claude Code) | The organization + execution layer. An orchestrator loads the right specialized agent + context per request. | Agent workspaces |

CS Lewis frame (Curtis's "head, chest, gut"): **head** = reason (Thinking), **chest** = trained values/sentiment (the Soul layer, Feeling+values), **gut** = instinct (Intuition/Sensing). "Anything short of that, it's just the average of the internet."

---

## Table 1 — The 8 Cognitive Functions

Two activities: **Perceiving** (taking in info: Sensing vs Intuition) and **Judging** (deciding: Thinking vs Feeling). Each runs in an **external** (e) or **internal** (i) attitude → 8 functions.

| Function | Process (what it does) | Strengths | Weaknesses | Does best | Suggested AI agent role |
|---|---|---|---|---|---|
| **Se** — External Sensing | Takes in tangible, concrete facts as-is, no added meaning. "Apple = red, shiny, crunchy." | Present, observant, literal accuracy, fast reaction | Misses implications/context, no synthesis | Capturing raw reality exactly as stated | Scraper / monitor / literal data collector / "what customers *actually* said" (the video's **Pike** half) |
| **Si** — Internal Sensing | Compares new input to stored past experience/data. "This apple reminds me of…" | Memory, consistency, precedent, detail recall | Anchored to the past, change-averse | Standards, SOPs, regression vs prior state | Archivist / SOP-keeper / consistency & compliance checker / version memory |
| **Ne** — External Intuition | One input → many possibilities, fanning outward (fireworks). Lateral connections. | Divergent ideation, optionality, hypotheses | Scattered, over-generates, won't converge | Generating many novel options/angles | Brainstormer / ideation / hypothesis generator (the video's **Leora**) |
| **Ni** — Internal Intuition | Many inputs → one distilled conclusion/pattern. Foresight. | Synthesis, strategy, "the underlying point" | Can be opaque, over-certain, slow to act | Distilling signal into one insight/strategy | Strategist / synthesizer / insight distiller (the video's **Malachi** + **Cash** pattern half) |
| **Te** — External Thinking | Judges valid/invalid by rules-of-thumb; prioritizes **efficiency**. "Get it done, what works." | Decisive, organized, execution, metrics | Can steamroll nuance/accuracy | Turning a decision into action & next steps | Orchestrator / PM / optimizer / executor (Malachi's judging half) |
| **Ti** — Internal Thinking | Judges by internal logical consistency; prioritizes **accuracy** over time. Builds frameworks. | Precision, rigor, debugging, depth | Slow, perfectionist, analysis paralysis | Deep correctness & logical frameworks | Analyst / debugger / logician / code & spec reviewer |
| **Fe** — External Feeling | Judges right/wrong by shared/social values; reads what others need. | Audience attunement, tone, harmony, persuasion | Over-accommodating, conflict-avoidant | Speaking to people; tone & relationship | Copywriter / community / support / brand-voice (Cash's feeling half) |
| **Fi** — Internal Feeling | Judges right/wrong by **personal/internal values**. Authenticity. | Integrity, conviction, mission-fit | Subjective, hard to externalize | Holding the line on values | **Values/ethics guardian, brand-integrity gate** — maps to your **Soul** layer (Pike's feeling half) |

---

## Table 2 — The 16 MBTI Types (full function stacks)

Stack order = **Hero** (dominant, most natural) → **Parent** (auxiliary, guides hero, opposite mode) → **Child** (tertiary, opposite attitude of parent) → **Inferior** (weakness/growth, opposite of hero). Code rules from the video: letter 1 = hero's attitude (I/E); letter 2 = N/S of strongest perceiving fn; letter 3 = T/F more natural; letter 4 = whether the strongest **external** function is **P**erceiving or **J**udging.

| Type | Stack (Hero·Parent·Child·Inferior) | Strengths | Weaknesses | Does best | Suggested AI agent role |
|---|---|---|---|---|---|
| **INTJ** | Ni·Te·Fi·Se | Strategy + decisive execution | Rigid, dismisses present detail | Turn a vision into an executable plan | Strategy-to-execution planner (Malachi-class) |
| **INTP** | Ti·Ne·Si·Fe | Logical depth + idea generation | Won't ship, over-analyzes | Diagnose logic, model systems | Analyst / architect / debugger |
| **ENTJ** | Te·Ni·Se·Fi | Drives outcomes, organizes | Impatient, bulldozes | Run an operation to a goal | Orchestrator / ops lead |
| **ENTP** | Ne·Ti·Fe·Si | Divergent + rigorous | Scattered, contrarian | Explore the option space | Brainstormer + stress-tester (Leora-class) |
| **INFJ** | Ni·Fe·Ti·Se | Insight + human attunement | Idealistic, opaque | Find the meaning + frame it for people | Message/brand strategist (Cash-class; Brooke & Tom) |
| **INFP** | Fi·Ne·Si·Te | Values + imagination | Avoids hard execution | Keep work true to values | Values guardian + creative writer |
| **ENFJ** | Fe·Ni·Se·Ti | Persuasion + vision | Over-extends to please | Mobilize people around a vision | Community / persuasion / DevRel |
| **ENFP** | Ne·Fi·Te·Si | Ideas + heart + drive | Loses focus | Inspire + generate on-mission ideas | Creative campaign / hook ideation |
| **ISTJ** | Si·Te·Fi·Ne | Reliable, precise, ordered | Inflexible to change | Execute a standard exactly | SOP executor / compliance / QA |
| **ISFJ** | Si·Fe·Ti·Ne | Careful, supportive, detailed | Avoids conflict/change | Steady support to a standard | Support / documentation / care |
| **ESTJ** | Te·Si·Ne·Fi | Organized, decisive, sequential | Blunt, rigid | Run tasks in order to completion | Task runner / PM (the video's **mom**) |
| **ESFJ** | Fe·Si·Ne·Ti | People-first, dependable | Needs approval | Keep a group aligned & served | Customer success / community ops |
| **ISTP** | Ti·Se·Ni·Fe | Hands-on logic, troubleshooting | Detached, terse | Fix the concrete problem now | Troubleshooter / tooling / debugger |
| **ISFP** | Fi·Se·Ni·Te | Aesthetic + values + present | Conflict-averse | Make it feel right in the moment | Visual/aesthetic + values check |
| **ESTP** | Se·Ti·Fe·Ni | Real-time, pragmatic, adaptive | Impulsive, short-term | React to live conditions fast | Live monitoring / rapid-response |
| **ESFP** | Se·Fi·Te·Ni | Energetic, present, people | Distractible | Engage an audience in the moment | Social / live-engagement |

---

## Table 3 — Cognitive Stack Combos (how a stack is built + the agent-assignment recipe)

Combination rules (from the video): functions come in **balanced pairs** — Se↔Ni, Ne↔Si, Te↔Fi, Fe↔Ti. If your hero **perceives**, your parent **judges** (and vice versa). The **child** is the opposite attitude of the parent; the **inferior** is the opposite of the hero. **You only need the top two (Hero·Parent) to spin up an agent** — the rest is forced. Organized by hero to show the construction logic.

| Hero (dominant) | Valid Parent (auxiliary) | → Full stack | → Type | Agent archetype + best task |
|---|---|---|---|---|
| **Ni** | Te | Ni·Te·Fi·Se | INTJ | **Strategist-Executor** — diagnose → exact next actions |
| **Ni** | Fe | Ni·Fe·Ti·Se | INFJ | **Message Strategist** — find the meaning, frame for audience |
| **Ne** | Ti | Ne·Ti·Fe·Si | ENTP | **Explorer-Analyst** — generate + pressure-test ideas |
| **Ne** | Fi | Ne·Fi·Te·Si | ENFP | **On-Mission Ideator** — ideas aligned to values |
| **Si** | Te | Si·Te·Fi·Ne | ISTJ | **Standards Executor** — run the SOP precisely |
| **Si** | Fe | Si·Fe·Ti·Ne | ISFJ | **Support Steward** — consistent, caring delivery |
| **Se** | Ti | Se·Ti·Fe·Ni | ISTP | **Troubleshooter** — fix the concrete problem now |
| **Se** | Fi | Se·Fi·Te·Ni | ISFP | **Aesthetic/Present** — make it feel right live |
| **Te** | Ni | Te·Ni·Se·Fi | ENTJ | **Orchestrator** — drive an operation to the goal |
| **Te** | Si | Te·Si·Ne·Fi | ESTJ | **Task Runner** — sequential, decisive completion |
| **Ti** | Ne | Ti·Ne·Si·Fe | INTP | **Architect/Debugger** — model & verify the logic |
| **Ti** | Se | Ti·Se·Ni·Fe | ISTP | **Hands-on Fixer** — pragmatic technical fixes |
| **Fe** | Ni | Fe·Ni·Se·Ti | ENFJ | **Persuasion/DevRel** — rally people around a vision |
| **Fe** | Si | Fe·Si·Ne·Ti | ESFJ | **Customer Success** — keep the group served & aligned |
| **Fi** | Ne | Fi·Ne·Si·Te | INFP | **Values Guardian + Writer** — keep work true + imaginative |
| **Fi** | Se | Fi·Se·Ni·Te | ISFP | **Integrity + Craft** — value-true, in-the-moment craft |

### Quick assignment heuristic (for routing tasks → agents)
- **Diverge / brainstorm / research options** → Ne hero (ENTP/ENFP) — *Leora*
- **Converge / strategy / one-insight synthesis** → Ni hero (INTJ/INFJ) — *Malachi, Cash*
- **Execute / orchestrate / drive to done** → Te hero (ENTJ/ESTJ) — *mom*
- **Analyze / debug / verify logic** → Ti hero (INTP/ISTP)
- **Audience-facing copy / community / tone** → Fe-strong (ENFJ/ESFJ; Cash uses Ni·Fe)
- **Values/ethics/brand-integrity gate** → Fi-strong → wire to the **Soul** layer
- **Exact-fact intake / monitoring / scraping** → Se hero (ESTP/ESFP; Pike uses Se·Fi)
- **Standards / SOP / consistency / QA** → Si hero (ISTJ/ISFJ)

---

## Provenance & open verification
- **Applied framework** (agent experiment, 18-agent build, Soul/Mind/Body, head/chest/gut): verified directly from the video transcript.
- **Function definitions + apple examples**: from the video (Brooke's slides), consistent with Jung/Briggs-Myers.
- **16 full function stacks (Table 2/3)**: standard Jungian-MBTI stacks, **audited clean by an adversarial sub-agent** against two independent authoritative sources (jobcannon.io, ourhumanminds.com; cross-checked vs Psychology Junkie / MyersBriggs.org). Confirmed to use the modern Harold Grant stack convention consistently. (2026-06-27)
- **Known discrepancy in the video**: Cash is described once as "same functions as Brooke" (Ni·Fe = INFJ) but his profile card later reads "ENFP 2w3" (Ne·Fi). Flagged, not resolved — doesn't affect the method.
