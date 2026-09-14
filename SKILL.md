---
name: decision-records
description: |
  Capture a project's decisions with their reasons in a lightweight,
  append-only record: each entry holds the decision, the alternatives
  considered, the why, and whether it is reversible; reopening a decision
  means writing a new entry that supersedes the old one. Use when a project
  makes a choice that is expensive to reverse or repeatedly re-argued, when
  the same debate keeps coming back, when onboarding someone into a project
  full of unexplained conventions, or when closing a session that made
  design or process choices.
  触发词：决策记录 / 记录决策 / 为什么这么做 / decision record。
license: MIT
metadata:
  version: "0.1.0"
---

# Decision Records: the why outlives the what

A decision whose reason lives only in chat history gets re-litigated every
few weeks. A decision record is one short entry — decision, alternatives,
why, reversibility — stored where the work happens.

## Rules

1. **Record decisions that are expensive to reverse or re-argue.** Routine
   choices stay in code and commits; a record earns its place when the
   choice is costly to undo or keeps coming back as a debate.
2. **The why is the payload.** "Use X" goes stale; "Use X because Y; we
   rejected Z" keeps teaching after the facts have moved on. An entry
   without the why is a rumor.
3. **Append-only.** Reopening a decision means writing a new entry that
   names and supersedes the old one. History stays readable; the evolution
   stays visible. Editing old entries in place is how records rot.
4. **Record at the moment of decision.** A record written later from memory
   documents the memory, not the reasoning.
5. **Keep it where the project lives.** One `decisions.md` at the project
   root, or a decisions section in the project's existing doc — a file
   nobody passes on their way to work is a file nobody reads.

## Steps

1. **Set up.** Create the record file at the project root with a one-line
   header explaining the format, and link it from the project's main doc.
   Done when: the file exists and is reachable from the project's entry
   document.
2. **Capture.** For each qualifying decision, write one entry: date,
   decision in one line, alternatives considered, the why, reversibility.
   Done when: each entry is five lines or fewer and carries all five fields.
3. **Supersede, never edit.** When a decision changes, append a new entry
   that names the old one and states what replaced it.
   Done when: the old entry remains untouched and the new entry names it.
4. **Point at the record.** Wherever the decision's effect shows up — code
   comment, config, doc — reference the entry by date.
   Done when: someone hitting the surprising choice finds the why one click
   away.

## Done when

The project's expensive decisions each carry a dated entry with decision,
alternatives, why, and reversibility; changed decisions are superseded by
new entries rather than rewritten; and the record lives where the next
contributor will actually pass it.
