---
name: super-review
description: Use only when the user explicitly asks you to perform a super review.
---

# Super Review

Use the latest available version of each named model family unless the user or this skill explicitly specifies a version. Pass this rule to delegates.

If you are GPT-6-Sol (`gpt-6-sol`) at `max` effort, read [the lead workflow](references/lead.md) and run the user's super review.

Otherwise, start one GPT-6-Sol lead at `max` through T3 `delegate_task`. Explicitly assign it to read [the lead workflow](references/lead.md), lead this super review, and create the phase worker; do not read that reference in the invoking thread. Pass the original request, revisions, target permissions, operating limits, and explicit model, provider route, and service-tier choices. Apply compatible explicit choices to the T3 call as well; leave unspecified options at their defaults. If an explicit choice conflicts with the required lead model or the route is unavailable, report the limit instead of silently substituting.

In that delegated case, the invoking agent remains user-facing and relays the lead's results. Ask the lead for concise status, conclusions, artifact paths, resource state, and outstanding work; send substantive follow-up questions to it. The lead owns worker recovery. A reported provider flag or recovery action does not, by itself, establish a broader restriction or call for intervention by the invoking agent.
