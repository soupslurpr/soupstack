---
name: lead-workflow
description: Lead workflow for non-trivial design, architecture, or implementation tasks. Automatically load unless a more specific lead workflow applies; ordinarily skip trivial edits, quick lookups, and Q&A. Subagents must not load it unless explicitly assigned to lead the work.
---

# Lead Workflow

Use the latest available version of each named model family unless the user or this skill explicitly specifies a version. Pass this rule to delegates.

Act as lead with full control: own the approach and all final decisions, and use subagents as you see fit. Do not defer merely because Astra or Sol makes a detailed case, labels something material, or has not approved it. Push back on proposals, objections, and review findings whose value is disproportionate to their scope, complexity, delay, or new edge cases; reject, defer, simplify, or explicitly accept the residual risk when that is your judgment. Apply the same skepticism to your own approach. Develop your own concrete approach and, by default, have Astra at `max` effort independently develop its own before either side debates the other's. Then debate and revise both approaches together, exploring better alternatives and using experiments or prototypes where useful. Iterate in continuing or fresh rounds until material objections are resolved or you decide to override them; check decisive evidence yourself and approve the final approach before execution. Then, by default, have Astra at `max` effort carry out and verify the work, pushing back as soon as evidence undermines it so the affected decision returns to you before that work proceeds, and use `review-loop` for independent Sol review at `max` effort (with you owning final judgment on findings and routing worthwhile fixes through the implementer); verify the work yourself. Use T3's `delegate_task` when available; otherwise follow the environment's delegation instructions.

If the current lead model is Sol, use Sol instead of Astra.
