---
name: review-loop
description: "Automatically get independent GPT Sol review before completing substantive code or configuration changes or opening a PR. Also use when explicitly requested. Ordinarily skip trivial edits. Re-read after context compaction. Delegated reviewers must not start another review loop."
---

# Review Loop

Use the latest available version of each named model family unless the user or this skill explicitly specifies a version. Pass this rule to delegates.

After implementation and relevant checks, have **GPT Sol at `max` effort** independently review the change. Keep the current implementer and use one reviewer per round. Stop when no fixes need review and no worthwhile objections remain.

Give each round a fresh reviewer context with the task, constraints, complete change (including uncommitted and new files), and validation results. Use judgment about sharing previous findings and responses: withholding them initially can reduce anchoring, while sharing them helps verify fixes and resolve objections. Ask the reviewer to assess the approach and implementation against the goals and constraints and identify real problems, design flaws, improvements, or unnecessary complexity. Reviewers inspect and test; they do not edit task files or start more review loops.

The implementer verifies each finding, fixes real issues within scope at their root cause, and validates the result. Rethink or redesign the underlying approach when findings expose a flawed design or keep recurring, rather than layering point patches or punting genuine bugs to end the loop. Do not yield merely because GPT Sol makes a detailed case, labels something material, or has not approved it: push back with reasons on false positives, issues outside our code or scope, or changes whose complexity or risk outweighs their value. For review-only requests, report findings without making fixes or repeatedly reviewing unchanged code.

Repeat when fixes need review or worthwhile objections remain. Keep the source stable during each review and track which version was reviewed; a HEAD SHA alone does not cover uncommitted changes. Keep the round count across continuations.

If GPT Sol cannot run, report the limitation instead of silently substituting another model. Follow the environment's delegation instructions and the task's existing authorization.

In the final response, briefly state the reviewer, effort, rounds, significant outcomes, and any rejected findings or review/validation gaps. Claim reviewer approval only for the exact version actually approved.
