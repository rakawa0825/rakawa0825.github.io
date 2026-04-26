---
layout: default
title: Human-in-the-Loop Design Review
category: articles
permalink: /articles/human-in-the-loop-design-review/
description: Human governance patterns for LLM-assisted infrastructure engineering workflows.
---

# Human-in-the-Loop Design Review

Human-in-the-loop design review is not just a safety disclaimer. In infrastructure engineering, it is a workflow requirement.

LLMs can help structure evidence, draft artifacts, and identify contradictions. They should not silently decide engineering scope, approve risk, or turn unresolved issues into accepted design.

## 1. LLMs Should Not Silently Decide Engineering Scope

Infrastructure decisions can affect reliability, security, operations, migration risk, and customer commitments. A generated document may sound confident, but confidence is not approval.

The workflow should make this boundary explicit. An LLM may extract a requirement from a source. It may identify that a branch needs special handling during migration. It may draft a delta report. But it should not decide that the exception is approved, that the risk is accepted, or that the design baseline has changed.

Those decisions belong to accountable humans.

This does not mean every step has to wait for a meeting. A workflow can still be efficient. The key is that the artifact should state whether an item is confirmed, pending, rejected, deferred, or assigned to detailed design. A reviewer should not have to infer decision status from tone.

## 2. Treat Uncertainty As An Output

Many workflows treat uncertainty as something to remove. That is dangerous. In real design review, uncertainty is often the most important output.

A useful artifact should show:

- What is confirmed by source evidence.
- What is an assumption.
- What is unresolved.
- What requires customer confirmation.
- What requires vendor confirmation.
- What should be handed off to detailed design.
- What requires human approval.

When uncertainty is visible, reviewers can act on it. When uncertainty is hidden, the team may accidentally build on an unsupported claim.

Treating uncertainty as an output also helps customer and vendor conversations. Instead of asking a broad question like "is this design correct," the team can ask targeted questions: Is this exception required? Who owns this confirmation? Does this behavior depend on configuration? Should this item move to detailed design?

## 3. Separate Facts, Assumptions, Unresolved Issues, And Approval Points

The separation has to appear in the artifacts, not only in the prompt.

A requirements table can include status, source ID, confidence, confirmation owner, and notes. An unresolved issue list can include owner, impact, next action, and approval need. A delta report can show previous understanding, new information, impacted artifact, recommendation, and human decision.

This structure makes review more concrete. A reviewer can challenge one row, one source reference, or one decision status. The workflow becomes easier to audit because the artifacts show why a conclusion exists.

This also reduces accidental overcommitment. A generated paragraph may imply that a decision has already been made. A table with explicit status and approval columns is harder to misread. It shows which parts of the design are evidence-backed and which parts still need action.

## 4. Human Governance In Design Workflows

Human governance should define what the LLM may do and what humans must approve.

LLMs may help with source inventory, terminology normalization, requirement extraction, contradiction detection, draft delta reports, update proposals, and approval checklists.

Humans must approve design decisions, scope commitments, risk acceptance, customer-facing language, unresolved issue closure, detailed-design handoff, publication, and production-impacting actions.

This boundary protects both the engineering team and the workflow. It allows LLMs to be useful without pretending they own accountability.

Governance should also be visible in the repository itself. Agent rules, templates, sample outputs, and validation reports should repeat the same boundary. If a rule matters only in a prompt, it is easy to lose. If it appears in artifacts and checks, it becomes part of the operating model.

## 5. How This Improves Review Readiness

Human-in-the-loop review improves readiness because it changes the shape of the output. Instead of a final-looking document, the team gets a reviewable package:

- Source manifest.
- Requirements table.
- Communication matrix.
- Unresolved issue list.
- Delta report.
- Design update proposal.
- Human approval checklist.

Each artifact has a purpose. Each one can be challenged. Each one can be improved. The workflow supports professional review instead of bypassing it.

That is the practical direction for LLM-assisted infrastructure work: not autonomous decisions, but better evidence, better review, and clearer human approval.

## Review Readiness As A Product Goal

Review readiness is a useful product goal because it is concrete. A workflow is review-ready when a technical reviewer can understand the source material, the extracted requirements, the unresolved issues, the proposed deltas, and the required approval points without needing private context.

This is especially important for public-safe portfolio work. The examples must be synthetic, but the workflow should still feel real. The goal is to demonstrate engineering judgment through structure: what is tracked, what is not claimed, what remains pending, and what requires human approval.

That kind of discipline is valuable beyond one project. It is a pattern for building LLM-assisted systems that can operate near real engineering work without pretending that the model is the owner of the decision.
