---
name: provocation
description: Edward de Bono's Provocation (Po) technique — state something deliberately wrong or absurd about the problem, then extract useful "movement" from it instead of judging it. Use when a constraint feels unbreakable, when every design converges on the same shape, or to escape "the way it's always done". Triggers include "provocation", "po", "absurd statement", "deliberately break the rule", "the constraint feels unbreakable", "sacred cow". Do NOT use for analytical work like debugging, code review, or implementation tasks.
---

# Provocation (Po)

## What this technique does

State something deliberately wrong, impossible, or absurd about the problem — then refuse to judge it. Instead, ask what *useful movement* the statement creates: the principle hiding inside it, what would happen moment-to-moment if it were true, what that makes different from today. The absurd statement is not a proposal; it is a stepping stone you stand on only long enough to reach somewhere you could not have walked to directly. It works because judgment and movement are opposite mental motions, and every honest constraint you carry is also a wall you have stopped seeing.

Source: Edward de Bono, *Po: Beyond Yes and No* (1972) and *Serious Creativity* (1992).

## Workflow

### Step 1: Confirm the target

A valid target is a concrete creative problem where the usual answers have gone stale: a design that keeps converging on the same shape, a constraint everyone treats as physics, a process nobody questions anymore. Good phrasings: "reinvent how we onboard new users", "our pricing page always ends up looking identical to competitors", "the approval step feels untouchable — challenge it". If the target is unclear, ask one focused question — "What's the problem, and which constraint or convention feels most fixed?"

Refuse requests to *perform* analytical work — debugging, reviewing code, implementing a change — and suggest an analytical approach instead. Redesigning or ideating *about* such a process is a valid creative target: "reinvent our code-review ritual" is in scope; "review this PR" is not.

### Step 2: Surface the rules

List 4–6 operating rules or constraints that everyone treats as fixed about the target. Write them as flat declaratives, not questions — the things so obvious nobody says them out loud. These are the walls. Each one is a candidate to break, invert, or exaggerate in the next step. If you cannot name at least four, the target is probably too vague; go back to Step 1.

### Step 3: Generate 4–6 provocations

Draw across the five classical operations. Prefix each with `Po:` and keep it to one line. A good Po is one you could not defend as a real suggestion — if it sounds reasonable, it is not a provocation yet, push it further.

- **Escape** — drop a rule entirely. Take a rule from Step 2 and state its absence as fact. `Po: the checkout has no prices.`
- **Reversal** — invert a relationship. Flip who does what to whom, or which direction something flows. `Po: the user reviews the software's work.`
- **Exaggeration** — push a quantity to an impossible extreme (up or down to zero). `Po: onboarding takes three seconds.`
- **Distortion** — scramble the normal sequence or swap the roles in it. `Po: you pay the invoice before the work is scoped.`
- **Wishful thinking** — state a fantasy as accomplished fact. `Po: the page reads the visitor's mind.`

Cover at least three of the five operations across the batch. Do not run more than eight in one batch.

### Step 4: Movement, per provocation

Never evaluate the provocation itself — do not ask whether it is good, safe, or possible. That is judgment, the wrong motion. Instead extract movement three ways:

- **(a) The principle** — what general idea is hiding inside the absurd statement?
- **(b) Moment-to-moment** — if it were literally true, what would happen, step by step, in the first minute?
- **(c) The difference** — what is concretely different from how things work today?

Then shape any live thread into a real idea. Not every provocation reaches one — that is expected and honest (see Honesty mechanics). Show the movement work, not just the idea it produced.

### Step 5: Meta-pattern scan

Scan across the ideas that landed for a structural property that kept recurring — "every provocation that paid off removed a step rather than adding one", "the strong ones all shifted work from the user onto the system", "three of them turned a cost into a signal". State the structural insight explicitly. This cross-provocation observation is often where the deepest result lives, and it also explains why the abandoned ones failed.

### Step 6: Spec-kill (mandatory)

Before ranking, check each candidate against *why* the rule it breaks exists. Look in the target's own record — spec sections like `Does NOT provide` / `Verdict`, proofs, invariants, model-checked properties. Reason is a proven invariant or a conclusion derived from one → the idea is **dead**: mark it `spec-kill: <invariant>` and keep it visible. Reason is habit, convention, or an untested assumption → the idea lives. No record to check (a fresh product idea) → say so in one line and move on. A provocation that rewords a guarantee ("Po: the certificate is an option") still hits the invariant that guarantee protects.

### Step 7: Honest ranking

Pick the 2–4 sharpest directions and rank them. Say which feel weak, and why. Then offer next moves and stop: run more provocations, go deeper on one direction, switch to a different technique, or stop here. Never push the user to commit — divergence is your job; the decision is theirs.

## Honesty mechanics

A provocation that yields no movement after two honest attempts is abandoned visibly. Show it, for example:

`Po: customers pay us to leave — no movement found. Moving on.`

Roughly 1 in 3 provocations will not pay off. A batch where every single Po produces a clean idea is a tell that the movement was faked — the operator judged the provocations into safe suggestions instead of moving off them. Show the failures; they are what proves the rest are real.

**When the batch itself fails.** If almost nothing moves, the problem is upstream of the provocations. Do not write more of them. Name the diagnosis, suggest the technique that fits it as the user's next move, and stop there — do not run it yourself:

- Step 2 could not produce four rules everyone treats as fixed → the target is too vague, or it is not actually fenced. Suggest `random-stimulus`, which needs no constraint to push against.
- The rules are real but every Po lands back on the same idea → you may be solving the wrong problem. Suggest `concept-fan`, which climbs to the concept the target serves.

## What NOT to do

- **Don't defend or attack the provocation.** It is not a proposal. Arguing "that would never work" or "actually that's reasonable" both miss the point — extract movement instead.
- **Don't generate polite, plausible provocations.** If a Po could pass as a genuine suggestion, it is not a provocation. Push it until it is clearly absurd.
- **Don't skip the movement structure.** Jumping straight from the Po to a finished idea hides the reasoning and usually smuggles in an idea you already had.
- **Don't run more than 8 provocations per batch.** Quality drops and the movement work gets rushed.

## References

- [`references/provocation-templates.md`](references/provocation-templates.md) — the five operations, with fill-in templates and worked one-line examples
- [`references/worked-example.md`](references/worked-example.md) — a real session showing the full shape, abandonment included
