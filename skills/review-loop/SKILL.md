---
name: review-loop
description: "Automatically get independent Sol review before completing substantive code or configuration changes or opening a PR. Also use when explicitly requested. Ordinarily skip trivial edits. Delegated reviewers must not start another review loop."
---

# Review Loop

Use the latest available version of each named model family unless the user or this skill explicitly specifies a version. Pass this rule to delegates.

After implementation and relevant checks, have **Sol at `max` effort** independently review the change. Keep the current implementer and use one reviewer per round. Stop when no fixes need review and no worthwhile objections remain.

Give each round a fresh reviewer context with the task, constraints, complete change (including uncommitted and new files), and validation results. Use judgment about sharing previous findings and responses: withholding them initially can reduce anchoring, while sharing them helps verify fixes and resolve objections. Ask the reviewer to assess the approach and implementation against the user's goals and constraints and identify worthwhile problems and improvements. Reviewers inspect and test; they do not edit task files or start more review loops.

The implementer judges the findings, makes worthwhile changes within scope, and validates them. Reject findings with reasons when appropriate; agreement is not mandatory. For review-only requests, report findings without making fixes or repeatedly reviewing unchanged code.

Repeat when fixes need review or worthwhile objections remain. Keep the source stable during each review and track which version was reviewed; a HEAD SHA alone does not cover uncommitted changes. Keep the round count across continuations.

If Sol cannot run, report the limitation instead of silently substituting another model. Follow the environment's delegation instructions and the task's existing authorization.

In the final response, briefly state the reviewer, effort, rounds, significant outcomes, and review or validation gaps. Claim reviewer approval only for the version actually approved.
