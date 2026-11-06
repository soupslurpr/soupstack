# soupstack

My personal agent skills, published as used.

These are the live skills from my own setup, not a generalized library.
This is how I currently work, and it will keep changing: skills can be
changed, removed, or added at any time as my workflow evolves.
Read a skill before installing it, expect to adapt it, and see
[My setup](#my-setup) below.

## Skills

- [grilling](skills/grilling/SKILL.md) — Interview the user in rounds of
  rigorous questions to stress-test a plan, decision, or idea before
  committing to it. Invoked when the user asks to be grilled. Adapted from
  Matt Pocock's skill of the same name; see [CREDITS](skills/grilling/CREDITS).
- [lead-workflow](skills/lead-workflow/SKILL.md) — The default lead agent
  workflow: own the approach, debate it with a strong subagent, approve it,
  then delegate execution and independent review. Loads automatically unless
  a more specific lead workflow applies. Subagents must not load it unless
  explicitly assigned to lead.
- [review-loop](skills/review-loop/SKILL.md) — Get independent review from a
  fresh-context reviewer before completing substantive code or configuration
  changes or opening a PR, then fix and re-review until no worthwhile
  objections remain. Loads automatically; skip for trivial edits.
- [super-review](skills/super-review/SKILL.md) — An extensive, phased review
  of a user-specified target, including security triage and reproducible
  issue bundles. Loads only when the user explicitly asks for a super review.

lead-workflow and review-loop are designed to compose (lead-workflow ends
with an independent review). super-review is a separate, explicit, much
heavier path. grilling stands alone.

## My setup

These were written for, and are only tested in, [my fork of T3
Code](https://github.com/soupslurpr/t3code) (recommended), with Muse
and Codex. T3's orchestrator can delegate child tasks across
providers, so a lead on one provider can hand work to models from another.
My fork also adds specifying the access program, such as Daybreak Blue,
when delegating, which upstream T3 Code did not have last I checked.
super-review needs that for its Daybreak Blue fallback; without Daybreak
Blue, super-review will be limited if a provider refusal stops a review.

I use Muse Wonder Full at `xhigh` reasoning effort as the lead: strong in
general, and especially at communication, orchestration, and keeping work
on track. `xhigh` rather than `max` because returns likely diminish above
it — extrapolating from Muse Spark 1.3 numbers — and because quota on the
$200 plan is limited.

Separate models debating each other helps because they bring different
opinions, positions, and ways of thinking. Astra debates and executes, and
Sol reviews, because OpenAI models are
strong at digging deep and finding issues. Sol in particular is a strong
yet relatively cheap reviewer, which matters for a skill that runs on every
substantive change. Opus would likely be a good substitute in the
debate role.

“Astra” and “Sol” mean the latest available version at `max` reasoning
effort, unless the user or a skill explicitly specifies a version.

lead-workflow itself does not name a lead model.

## License

My own material is under the [MIT License](LICENSE). grilling is adapted
from Matt Pocock's MIT-licensed work, so his copyright and license notice
apply to his part of it; they are preserved in
[skills/grilling/CREDITS](skills/grilling/CREDITS).
