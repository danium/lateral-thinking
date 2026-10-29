---
name: inversion
description: Assumption Inversion — list the assumptions behind the current approach and flip each one, then ask where the flipped version could actually be true. Use when requirements encode beliefs nobody has questioned, when a design feels inevitable, or when incumbents all share one blind spot. Triggers include "invert", "flip it", "flip the assumption", "reverse the premise", "what if the opposite were true", "challenge the assumption". Do NOT use for analytical work like debugging, code review, or implementation tasks.
---

# Assumption Inversion

## What this technique does

Every approach rests on a stack of unstated beliefs — about who the user is, what they value, how the thing gets delivered, in what order, at what price. List those beliefs, flip each one into its opposite, then ask the sharp question: where is the flipped version *already true*? Most flips are dead ends, and naming them dead is part of the work. The two or three flips that turn out to be true somewhere are where a non-obvious direction hides — the incumbents never looked there because the original belief felt like a law of nature.

Source: the classical dialectic method of arguing a position by its negation; popularized for business by "invert, always invert" (Carl Jacobi, via Charlie Munger) and by Edward de Bono's reversal method in *Lateral Thinking* (1970).

## Workflow

### Step 1: Confirm the target

A valid target is a design, plan, or approach whose assumptions you can list: a product strategy, a go-to-market plan, a pricing model, a workflow you are about to build, an onboarding sequence. If the target is unclear, ask one focused question — "What's the current approach, and what feels locked-in about it?"

Refuse requests to *perform* analytical work — debugging, reviewing code, implementing a change — and suggest an analytical approach instead. Redesigning or ideating about such a process is a valid creative target: "reinvent our code-review ritual" is in scope; "review this PR" is not.

### Step 2: Extract the assumptions

List 5–8 assumptions behind the current approach. Aim for the load-bearing ones, not decorations. These prompt categories help you cover the space rather than list five versions of the same belief:

- **The user** — who they are, what they already know, what they can be trusted to do.
- **The value** — what the thing is actually worth, and to whom.
- **The channel** — where it reaches people and where they meet it.
- **The sequence** — what has to happen first, second, last.
- **The price** — who pays, how much, and when.
- **The effort split** — who does the work, the provider or the user.

### Step 3: Flip each assumption

Turn each assumption into its strongest *plausible opposite* — not a strawman. "Users want it fast" flips to "users want it slow and deliberate," not "users want it broken." A good flip is one a reasonable person could defend. If the flip is obviously stupid, you flipped it lazily; find the version a competitor could actually build a business on.

### Step 4: Hunt for where the flip is true

For each flip, ask the load-bearing question: **"In what market, segment, or era is this flip TRUE? Who profits from it today?"** Name a real place it holds — a customer type, an industry, a historical moment, an existing product. If you cannot name one honestly, the flip is dead. Say so and move on. Do not manufacture a fake "where."

### Step 5: Spec-kill (mandatory)

Before ranking, check each candidate against *why* the rule it breaks exists. Look in the target's own record — spec sections like `Does NOT provide` / `Verdict`, proofs, invariants, model-checked properties. Reason is a proven invariant or a conclusion derived from one → the idea is **dead**: mark it `spec-kill: <invariant>` and keep it visible. Reason is habit, convention, or an untested assumption → the idea lives. No record to check (a fresh product idea) → say so in one line and move on. Flip assumptions, not conclusions: a limit the record derives from a proof is a theorem, and flipping it flips the theorem.

### Step 6: Develop the survivors

Take the 2–3 flips that survived Steps 4–5 and develop them into concrete directions. What would the approach look like if you built it around the flipped belief? Where the flip already works for someone else, borrow the mechanism.

### Step 7: Meta-pattern scan

Scan across the flips that survived. Is there a structural insight — one belief that several assumptions all secretly depended on, one axis where the whole approach is fragile? State it explicitly. This cross-flip observation is often the real finding, larger than any single flipped assumption.

### Step 8: Honest ranking

Rank the surviving directions, weakest called out as weak and why. Mark the dead flips as dead so the user sees the whole map. Then offer the next move — extract more assumptions, go deeper on one direction, switch technique, or stop — and never push the user to commit. The technique is divergent; convergence belongs to the user.

## Honesty mechanics

**Dead flips stay visible.** A flip with no honest answer to "where is this true?" is marked dead explicitly, not quietly dropped. The dead flips are evidence the exercise was genuine.

**Something usually survives inversion unscathed.** At least one assumption, when flipped, has no live answer anywhere — the original belief really is close to a law for this problem. Say so. That is a finding too: it tells you where *not* to waste effort.

**Every flip working is a red flag.** An inversion session where every flip "turns out to be true somewhere" is a sign the flips were strawmen or the "wheres" were manufactured. Expect one or two flips to die.

## What NOT to do

- **Don't flip into absurdity.** Flipping "users want it fast" into "users want it broken" is a different technique's job (that is `provocation`'s territory). Inversion flips into *plausible opposites* a competitor could defend.
- **Don't stop at the flip.** The flip alone is a debating trick. The value is in Step 4 — hunting for where the flipped belief is already true. A flip with no "where" hunt is half the technique.
- **Don't flip more than 8 assumptions.** Depth beats coverage. Better to develop three survivors fully than to list twelve flips and hunt none of them.

## References

- [`references/worked-example.md`](./references/worked-example.md) — a real session showing the full shape, dead flips included
