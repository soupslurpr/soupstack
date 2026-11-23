# soupstack

My personal agent skills, published as used.

These are the live skills from my own setup, not a generalized library.
This is how I currently work, and it will keep changing: skills can be
changed, removed, or added at any time as my workflow evolves. Read a
skill before installing it, expect to adapt it, and see
[My setup](#my-setup) below.

## Skills

- [grilling](skills/grilling/SKILL.md): Interview the user in rounds of
  rigorous questions to stress-test a plan, decision, or idea before
  committing to it. Invoked when the user asks to be grilled. Adapted from
  Matt Pocock's skill of the same name; see
  [CREDITS](skills/grilling/CREDITS).
- [lead-workflow](skills/lead-workflow/SKILL.md): Default lead workflow
  for non-trivial design, architecture, or implementation tasks. The lead
  commits its own design, debates unanchored cross-lab partners in
  parallel (skipping debate when the approach is straightforward), settles
  and implements the work directly, and finishes with `review-loop`—pushing
  back on disproportionate proposals or findings instead of deferring to
  them. Loads automatically for leads; skip trivial edits, quick lookups,
  and Q&A.
- [review-loop](skills/review-loop/SKILL.md): Independent review from a
  fresh-context reviewer before completing substantive code or
  configuration changes or opening a PR, fixing and re-reviewing until no
  worthwhile objections remain. Loads automatically; skip trivial edits.
- [super-review](skills/super-review/SKILL.md): Extensive, phased review
  of a user-specified target, including security triage and reproducible
  issue bundles. Loads only when explicitly requested.

`lead-workflow` and `review-loop` compose (`lead-workflow` ends with an
independent review). `super-review` is a separate, much heavier explicit
path. `grilling` stands alone.

## My setup

### Environment

These skills are written for, and only tested in, [my fork of T3
Code](https://github.com/soupslurpr/t3code), using Antigravity, Codex, and
Muse Code. The fork is linked because it is what I use, not as a general
recommendation: it is only tested on my desktop and laptop, both running
x86-64 Arch Linux with GNOME on Wayland.

T3's orchestrator delegates child tasks across providers, so a lead on one
provider can work with models from another. My fork also supports
specifying an access program (such as Daybreak Blue) when delegating,
which upstream T3 Code did not have last I checked. `super-review` relies
on that for its Daybreak Blue fallback; without it, `super-review` will be
limited if a provider refusal stops a review.

### Models

Unless a skill or the user specifies a version, named model families mean
the latest available version.

- **Lead:** I use Gemini 4 Neon (via Antigravity) at `high` effort—fast,
  intelligent, and understanding, especially on long-horizon work,
  orchestration, implementation, and keeping things on track. Claude Opus
  would likely also be a good substitute as lead. `lead-workflow` itself
  does not name a lead model.
- **Debate panel (`lead-workflow`):** GPT Astra (`max`), Muse Wonder Full
  (`max`), Gemini Neon (`xhigh`), and Claude Opus (`max` on Claude, `high`
  on Antigravity), skipping whichever partner shares the lead's lab and
  continuing with the rest if a partner hits quota or is unavailable.
  Developing approaches independently across labs before debating brings
  genuinely different perspectives without anchoring on whoever proposed
  first.
- **Reviewer (`review-loop`):** GPT Sol (`max`). OpenAI models are strong
  at digging deep and finding issues, and GPT Sol in particular is strong
  yet relatively cheap—which matters for a skill that runs on every
  substantive change.

## License

My own material is under the [MIT License](LICENSE). `grilling` is adapted
from Matt Pocock's MIT-licensed work, so his copyright and license notice
apply to his part of it; they are preserved in
[skills/grilling/CREDITS](skills/grilling/CREDITS).
