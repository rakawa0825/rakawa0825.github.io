---
layout: default
title: Turning Fragmented Infrastructure Evidence into Reviewable Design Decisions
category: articles
permalink: /articles/turning-fragmented-infrastructure-evidence-into-reviewable-design-decisions/
description: A source-backed workflow pattern for turning fragmented infrastructure project evidence into reviewable, human-approved design decisions.
---

# Turning Fragmented Infrastructure Evidence into Reviewable Design Decisions

I am not trying to make AI own engineering decisions.

I am building workflow structures that help engineers turn fragmented infrastructure information into reviewable, traceable, and human-approved decisions.

That positioning matters because infrastructure design is not just a writing task. It is a review process shaped by source evidence, unresolved questions, operational constraints, and human approval boundaries.

## The problem: infrastructure design evidence is fragmented

Enterprise infrastructure design work rarely starts from a clean source of truth. Important information is often scattered across meeting notes, review comments, vendor answers, existing design documents, technical references, unresolved issues, and human approval decisions.

Each source can carry a different level of authority. A meeting note may capture intent but not approval. A vendor answer may clarify behavior but not define the customer's design requirement. An existing design document may describe the current baseline but not approve a new change. A review comment may identify a risk without deciding how to resolve it.

The practical problem is not only that information is messy. The problem is that design teams need to know what each statement means, where it came from, whether it is current, and who must approve it before it becomes design language.

## Why one-shot LLM generation is not enough

A tempting approach is to ask an LLM to generate a final design update in one step. For infrastructure work, that shortcut is unsafe.

One-shot generation can lose source context, promote assumptions into facts, hide uncertainty, close unresolved items too early, and imply approval that humans have not given. A polished paragraph can make a tentative statement look authoritative. A confident summary can blur the boundary between a proposed change and an approved design decision.

The safer pattern is not to avoid LLMs. It is to constrain their role. The workflow should ask the model to structure evidence, preserve uncertainty, identify impact, and prepare review artifacts. It should not let the model approve final design decisions.

## A source-backed workflow instead

The workflow pattern I am exploring looks like this:

```text
Fragmented project evidence
-> Source Registry
-> Extraction
-> Impact Analysis
-> Artifact Map
-> review_required / human approval
-> Reviewable design patch
-> Operational handoff
```

The Source Registry records what sources exist, what type they are, how authoritative they are, and which artifacts they may affect.

Extraction separates confirmed facts, assumptions, unresolved issues, proposed changes, and detailed-design handoff items.

Impact Analysis identifies which design domains may be affected, such as communication matrix, routing, security boundary, monitoring, and failover behavior.

The Artifact Map links sources and extracted review items to the documents or review artifacts they may change.

The `review_required` state keeps ambiguous or approval-gated items visible. It prevents draft outputs from becoming approved design language.

The final output is a reviewable design patch and operational handoff package, not an automatic production update.

## The Review-to-Patch pattern

A smaller version of the pattern is:

```text
review comment
-> source context
-> decomposed item
-> impacted artifact
-> draft design patch
-> human approval checklist
```

This pattern helps convert review comments into structured artifacts without losing the source context behind them.

For example, a synthetic review comment might say that a branch site may need a new flow through a cloud security service. That statement alone is not enough to update a design. The workflow should ask:

- Which source made the statement?
- Is the traffic flow confirmed or only proposed?
- Is the inspection scope known?
- Does routing or QoS treatment remain ambiguous?
- Does any item belong in detailed design rather than the main design document?
- Who must approve the patch before it is reflected?

The LLM Infra Design Studio repository includes a minimal synthetic Review-to-Patch dataset that demonstrates this flow. It uses fictional identifiers and public-safe examples only.

## Human approval is not optional

LLMs may structure information, surface contradictions, draft review questions, and prepare review artifacts.

Humans must approve final design decisions, customer-facing wording, production-impacting changes, risk acceptance, unresolved issue closure, detailed design handoff, and artifact reflection.

This boundary is not a limitation added after the fact. It is part of the workflow design. In infrastructure environments, the difference between "suggested," "review_required," and "approved" matters.

## What the prototype demonstrates

LLM Infra Design Studio currently demonstrates a Markdown-first structure for this workflow.

The repository includes:

- a README entrypoint,
- an anonymous case study,
- a Review-to-Patch Pipeline,
- a Source Context Card schema,
- a minimal synthetic example dataset,
- a CLI Validation Runner,
- public-safe validation checks.

The validation scripts check repository structure, sample outputs, source registry assets, LLM contract fixtures, failure-mode behavior, unresolved assertions, expected-output drift, and sensitive identifier hygiene.

This does not make the project ready for production use. It makes the workflow inspectable.

## What this is not

This is not a self-directed infrastructure design system.

It is not a network design tool ready for production use. It does not substitute for qualified engineers. It is not a repository for real customer data. It is not a SaaS product. It does not claim correctness by default.

The purpose is narrower and more practical: define a workflow structure that helps human reviewers turn messy evidence into source-backed design review artifacts.

## Why this matters

The future value of LLMs in enterprise infrastructure is not just text generation. The deeper value is helping teams transform messy project evidence into structured, reviewable, source-backed, human-approved workflow outputs.

That requires more than prompts. It requires source handling, review states, failure-mode tests, validation scripts, and clear human approval boundaries.

When those pieces are explicit, an LLM-assisted workflow can make expert review faster and clearer without pretending that the model owns the engineering decision.

## Repository

Repository: [LLM Infra Design Studio](https://github.com/rakawa0825/llm-infra-design-studio)

The repository uses synthetic examples only and is intended as a public-safe workflow prototype.
