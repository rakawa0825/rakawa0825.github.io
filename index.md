---
layout: default
title: Home
description: LLM-assisted infrastructure design lifecycle and workflow automation.
---

# Naoyuki Hirakawa

I design LLM-assisted workflows that turn fragmented infrastructure design information into traceable, reviewable, and human-approved engineering artifacts.

## About

My work focuses on the practical boundary between enterprise infrastructure engineering and AI-assisted workflow automation. I build workflows for network design review domains where engineers need traceable evidence, visible uncertainty, validation checks, and explicit human approval before design language becomes authoritative.

This site is a public-safe technical portfolio for English readers. It explains reusable workflow patterns rather than private project details.

## Featured Project

[LLM Infra Design Studio]({{ '/projects/llm-infra-design-studio/' | relative_url }}) is a Markdown-first workflow prototype for the LLM-assisted infrastructure design lifecycle. The public-safe v1.0 private preview demonstrates source manifests, requirement extraction, design logic review, semantic delta detection, artifact updates, a CLI validation runner, LLM contract and failure-mode validation, and human approval gates.

Repository: private preview / available upon request

## Design Philosophy

- LLMs should structure evidence before drafting conclusions.
- Uncertainty should remain visible as assumptions, unresolved issues, and confirmation items.
- Human approval should be part of the workflow, not an afterthought.
- LLM contracts and failure-mode checks should be explicit before generated artifacts are trusted.
- Markdown-first systems are useful before SaaS UI because they are inspectable, versionable, and easy to review.
- Validation should start small and run locally before the workflow grows.

## Articles

- [Building an LLM-Assisted Infrastructure Design Lifecycle]({{ '/articles/building-llm-assisted-infrastructure-design-lifecycle/' | relative_url }})
- [Markdown-First Workflow Products]({{ '/articles/markdown-first-workflow-products/' | relative_url }})
- [Human-in-the-Loop Design Review]({{ '/articles/human-in-the-loop-design-review/' | relative_url }})

## Public-Safe Boundary

This site does not include private project data, real customer names, real meeting transcripts, production network diagrams, or real review comments. Examples are synthetic and are used only to explain workflow structure.
