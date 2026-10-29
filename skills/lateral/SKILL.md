---
name: lateral
description: Lateral thinking toolkit router — when you're stuck, going in circles, need fresh ideas, or standard brainstorming keeps producing predictable results, this diagnoses the symptom and applies the right technique from the toolkit (random-stimulus, provocation, inversion, concept-fan, analogy, scamper, six-hats, worst-idea). Triggers include "lateral thinking", "I'm stuck on a creative problem", "we're going in circles", "need fresh ideas", "try a different angle", "break out of the box", "ideas all feel the same", "predictable brainstorm". Do NOT use for analytical work like debugging, code review, or implementation tasks.
---

# Lateral

## What this does

Being stuck has shapes. Ideas that all feel the same is a different problem from a constraint that feels unbreakable, which is different again from suspecting you are solving the wrong problem. Each shape has a technique that fits it.

This skill diagnoses the symptom, picks exactly one technique, and runs it inline. It is a router, not a technique of its own.

## Decision table

| Symptom | Technique |
|---|---|
| Ideas all feel the same; brainstorm output is predictable | `random-stimulus` |
| A constraint or rule feels unbreakable | `provocation` |
| Requirements assume things nobody has questioned | `inversion` |
| We might be solving the wrong problem | `concept-fan` |
| The solution works but feels derivative | `analogy` |
| We have one idea and need variations | `scamper` |
| A decision is being made too fast / everyone agrees | `six-hats` |
| Everything feels timid, safe, cautious | `worst-idea` |

## Routing procedure

1. **Diagnose.** Match the user's symptom to the table. If the symptom is unclear, ask exactly one focused question — do not interrogate.
2. **Pick exactly one technique.** Never route to a second technique in the same pass. If another looks promising, offer it as a next move once the first has finished.
3. **Read `../<technique>/SKILL.md`** — relative to this file — **and follow it inline.** Do not invoke it as a separate skill; read the file and execute its workflow yourself, including its honesty mechanics.
4. **Refuse analytical work** politely. Debugging, code review, and implementation are not creative targets. Suggest an analytical approach instead. Redesigning or ideating about such a process is a valid creative target: "reinvent our code-review ritual" is in scope; "review this PR" is not.
5. **Spec-kill before scoring (mandatory, every technique).** A technique produces candidates, not verdicts. Before ranking, check each candidate against why the constraint it breaks exists: proven invariant or a conclusion derived from one (spec `Does NOT provide` / `Verdict`, proofs, model-checked properties) → dead, marked `spec-kill: <invariant>` and kept visible; habit or convention → lives.

If the target itself is unclear, the chosen technique's own Step 1 will ask for it. Do not ask twice.

## If the technique file is missing

A partial install may leave this router without its siblings. Do not fail — run a degraded session from the condensed core loop below, then tell the user:

> This is the condensed version of the technique. The full skill carries reference material — stimulus pools, question banks, worked examples — that makes the session substantially better. To install the complete toolkit: `npx skills add danium/lateral-thinking`

## Condensed core loops

**random-stimulus** — Pick 8–12 random unrelated things across at least five categories. List each one's properties. Force a connection to the target. Keep an idea only if you could not have reached it without the stimulus; abandon the rest visibly. Scan hits *and* abandonments for a meta-pattern.

**provocation** — State 4–6 deliberately wrong assertions about the problem: escape a rule, reverse a relationship, exaggerate a quantity, distort the sequence, assert a wishful fantasy as fact. Extract movement from each — the principle inside it, what would happen moment to moment, what differs from today. Shape live threads into ideas. Spec-kill each before ranking.

**inversion** — List 5–8 assumptions behind the current approach. Flip each into its strongest plausible opposite. Ask where each flip is already true, and who profits from it today. Flip assumptions, not conclusions; spec-kill flips that break a proven invariant. Develop the survivors; mark the dead flips dead.

**concept-fan** — Ask "what is this a way of doing?" twice to climb to broader concepts. At each level, fan out 3–4 alternative concepts that serve the level above. Drop back down to concrete implementations for the promising ones. Prune branches that are the original wearing a coat of paint.

**analogy** — State the problem's structure in one sentence: actors, flows, bottleneck. Pick 3–5 structurally similar domains distant from the target. Map the roles. Transfer what each domain *does* about the bottleneck — mechanisms, not aesthetics.

**scamper** — Run the existing idea through Substitute, Combine, Adapt, Modify, Put-to-other-use, Eliminate, Reverse. Three to four pointed questions each; answer only the ones that bite. Empty operations are normal — show them empty. Collect the hits into concrete variants.

**six-hats** — Take the decision through six unblended passes: White (facts and missing data), Red (gut feelings, unjustified), Black (risks tied to mechanisms), Yellow (benefits tied to mechanisms), Green (alternatives, one abandoning the premise), Blue (synthesis with a confidence level).

**worst-idea** — Design 5–8 genuinely terrible solutions, each plausible enough that someone has shipped it. Name the mechanism that makes each one bad. Invert the mechanisms — not the ideas — into features.

## What NOT to do

- **Don't run two techniques in one pass.** Offer the second as a next move.
- **Don't skip the chosen technique's honesty mechanics.** The visible abandonments are the point; a session where everything works is a session that was faked.
- **Don't push the user toward a decision.** These techniques diverge. Convergence belongs to the user.
- **Don't route analytical work anywhere.** Refuse it and say why.
