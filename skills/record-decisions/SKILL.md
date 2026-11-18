---
name: record-decisions
description: Keep material product, architecture, scope, authority, compatibility, and sequencing decisions in the project's durable decision register before implementation or delegation; use whenever such a decision is settled, changed, rejected, superseded, implemented, reviewed, or committed.
---

# Record Decisions

Use this skill to prevent settled decisions from living only in chat,
compaction summaries, temporary briefs, or delegate reports.

## When this applies

Apply it when a material decision is settled, changed, rejected, or
superseded, and before implementing, delegating, reviewing, or committing work
that depends on such a decision.

A decision is material when it affects user-visible behavior, architecture,
scope or non-goals, authority or safety, data or compatibility, external
interfaces, sequencing, or a rejected alternative that could plausibly be
revived later. Do not use this skill for routine implementation details or
bug fixes that make no such decision, unless they reveal one.

## Hard gate

If a material decision exists only in conversation, implementation is not
ready to start. Record it first, or explicitly mark the unresolved part open
and do not silently absorb it into the implementation.

## Find the register

1. Use the project's existing durable decision register if it has one. It may
   be a single `DECISIONS.md`, an index plus topic files under
   `docs/decisions/`, an ADR directory, or an equivalent project convention.
2. If none exists and the project has ongoing material decisions, create
   `DECISIONS.md` at the owning project root as the short index, with grouped
   topic files under `docs/decisions/`, starting with only the topic files
   needed, unless project instructions name a better location or shape. In a
   monorepo, use the nearest owning project or package register; reserve any
   root register for cross-cutting decisions.
3. For a split register, keep the index as the canonical entry point:
   maintenance rules, status vocabulary, current boundary, topic links, and
   consolidated open and superseded indexes. Each detailed decision has one
   owning topic or decision file. Link or summarize from the index; do not
   duplicate detailed rationale there. Cite split entries by stable
   `file.md#heading` where available, and cross-link related entries instead
   of copying them.
4. Keep design/specification documents as the concise present-tense target.
   The register preserves status, rationale, scope, rejected alternatives,
   open details, and evidence. If the register and specification disagree,
   treat that as a defect and reconcile both in the same change.

## Record each decision

Before steering implementation or delegation, add or amend an entry with:

- **Decision:** the exact behavior or constraint in normative language.
- **Status:** shipped, implemented but uncommitted, settled but
  unimplemented, open, deferred, superseded, or rejected. Adapt labels only
  when the project already has equivalent statuses.
- **Why:** the user rationale, concrete hazard, evidence, or comparison that
  decided it.
- **Scope / not included:** adjacent behavior explicitly excluded.
- **Open details:** choices still owned by a later design, experiment, or
  slice. Do not present guesses as settled.
- **Evidence:** specification section, commit, test, report, or other durable
  reference once available.
- **Supersedes / rejected:** earlier decisions or alternatives replaced by
  this entry, when reviving them would be a plausible mistake.

Do not silently rewrite history. Mark replaced decisions superseded or
rejected, name the replacement, and keep the reason for the change.

## Use the register during work

- Implementation, delegation, and review briefs must cite the relevant
  decision entries, by stable file and heading where available, and the
  relevant specification sections instead of relying on chat history as the
  source of truth.
- Implementers must flag implemented behavior that has no register entry, and
  must not invent a missing decision silently.
- Reviewers must check both directions: recorded decisions that were not
  implemented, and implemented behavior that was not recorded.
- Temporary briefs, delegate reports, test counts, and compaction summaries
  are evidence or working notes, not replacements for the register.

## Boundary audit

At each slice, milestone, review, or commit boundary, audit three sources
against each other:

1. Material decisions settled in conversation since the last boundary.
2. The decision register. For a split register, enumerate the index and all
   linked register files, not only files touched by the diff.
3. The specification and actual code/diff.

Before calling the boundary complete:

- Add any missing decisions and rejected alternatives.
- Reconcile specification text that the decision makes stale.
- Update statuses honestly, such as settled to implemented or shipped, only
  when the corresponding review, verification, commit, or release step has
  actually happened.
- Move unresolved choices to an explicit open list with their owning step.
- Check split-register index links, consolidated open items, and superseded
  directions against their owning entries.
- Report remaining contradictions instead of guessing which source is right.

## Limits

Follow explicit user or project instructions that name a different decision
system. Do not record secrets, routine progress, every file touched, or
detailed implementation evidence that belongs in commits, tests, or reports.
