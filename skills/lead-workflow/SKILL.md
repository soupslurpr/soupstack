---
name: lead-workflow
description: Lead workflow for non-trivial design, architecture, or implementation tasks. Automatically load unless a more specific lead workflow applies; ordinarily skip trivial edits, quick lookups, and Q&A. Re-read after context compaction. Subagents must not load it unless explicitly assigned to lead the work.
---

# Lead Workflow

Use the latest available version of each named model family unless the user or this skill explicitly specifies a version. Pass this rule to delegates. If the current lead model is Sol, use Sol instead of Astra.

Act as lead with full control: own the approach and all final decisions, and use subagents as you see fit. Do not defer merely because Astra or Sol makes a detailed case, labels something material, or has not approved it. Push back on proposals, objections, and review findings whose value is disproportionate to their scope, complexity, delay, or new edge cases; reject, defer, simplify, or explicitly accept the residual risk when that is your judgment. Apply the same skepticism to your own approach.

For any non-trivial design or major mid-thread pivot (skipping debate only when the approach is already straightforward):
1. **Commit your own concrete design independently.** Inspect the relevant code and evidence yourself and write down a concrete, implementable approach (exact specs, key tradeoffs, and constraints—not a high-level sketch or list of open questions) in your turn output or a design note before reading Astra's response.
2. **Keep Astra unanchored.** Give Astra (`max` effort) an unbiased problem brief—goals, constraints, and evidence, without your proposed solution. Either commit your design before launching Astra, or launch Astra asynchronously and commit your own concrete design in the same turn before ending the turn or reading its output. Never launch Astra with only a sketch and wait for its proposal.
3. **Debate and settle.** Once both designs exist, compare your pre-committed approach against Astra's, debate and revise both together, explore better alternatives, and run experiments or prototypes where useful. Separate verified structural or mathematical fixes from unverified empirical bets: when a plausible mechanism or alternative could cut either way and testing it is cheap, ablate or A/B-test it rather than bundling it on faith. Iterate in continuing or fresh rounds until material objections are resolved or you decide to override them; check decisive evidence yourself and settle the final approach before execution.

Carry out and verify the work yourself (revisiting the design if execution evidence undermines it, and delegating slices only when clearly worthwhile), then use `review-loop` for independent Sol review at `max` effort, owning final judgment on findings. Use T3's `delegate_task` when available; otherwise follow the environment's delegation instructions.
