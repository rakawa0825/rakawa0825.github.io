---
layout: default
title: Markdown-First Workflow Products
category: articles
permalink: /articles/markdown-first-workflow-products/
description: Why Markdown is a useful starting point for LLM-assisted workflow products.
---

# Markdown-First Workflow Products

Many AI workflow ideas start with a UI. I think some should start with Markdown.

Markdown-first workflow products are not less serious. For early engineering workflows, Markdown can be the most direct way to make assumptions, artifacts, validation, and review visible before the system grows into a CLI, API, or SaaS product.

## 1. Markdown As Operational Structure

Markdown is simple, but it can hold a lot of operational structure. A repository can contain source manifests, requirement tables, unresolved issue lists, delta reports, design update proposals, approval checklists, and review reports. These files are readable by humans and easy for LLMs to generate or update.

The advantage is inspectability. A reviewer can open a file, read the artifact, check the source references, and comment on the exact lines that need correction. A Git diff shows whether a change is a real design update or only an editorial edit.

For LLM-assisted workflows, that matters. The output should not be a black box.

## 2. Agents, Skills, Workflows, Templates, State Files

A Markdown-first product can still have architecture.

Agents define role boundaries. Skills describe reusable process units. Workflows define the lifecycle. Templates define expected output formats. State files keep decisions, issues, approvals, and deltas visible across cycles.

This structure helps prevent a common problem: asking one model to do everything in one step. A lifecycle can split the work into smaller artifacts. One step creates a source manifest. Another extracts requirements. Another reviews design logic. Another checks validation. Another records approval points.

The result is less dramatic than a polished generated design, but it is more reviewable.

The same structure also helps teams talk about ownership. A governance role can own approval boundaries. An architecture role can review end-to-end consistency. A network role can review routing, redundancy, and connectivity logic. A verification role can check quality gates. An artifact role can keep output formatting consistent.

Those boundaries do not need to be perfect in v0.1. They need to be explicit enough that a reviewer can see where decisions should happen and where they should not.

## 3. Why Not Start With SaaS UI

A SaaS UI can be useful later, but it can also hide weak workflow design. Buttons and dashboards do not solve unclear ownership, missing source evidence, or vague approval boundaries.

Starting with Markdown forces the workflow to be explicit. What files exist? What does each file prove? What does each template require? What should a validation script check? What must remain human-owned?

Once those questions are answered, a UI has something real to expose.

## 4. Where Python Validation Fits

Small validation scripts are enough for a v0.1 workflow. They can scan for risky identifiers, check required headings, validate table columns, detect risky certainty phrases in unresolved sections, and compare sample outputs against expected behavior.

These scripts do not prove the system is complete. They show that the workflow has an executable quality posture. That is a useful starting point because it turns review expectations into commands that can run locally.

Validation also changes how the team writes artifacts. If the output has to pass simple checks, templates become more consistent. If unresolved assertions are scanned, the workflow is less likely to hide open issues.

The important point is that validation should match the maturity of the product. Early scripts can be intentionally small and readable. A reviewer should be able to open them and understand the safety checks in a few minutes. As the workflow becomes more important, validation can grow into stricter schema checks, additional eval cases, and eventually automated workflow tests.

## 5. Future Path Toward API And SaaS

Markdown-first does not mean Markdown-only forever.

The future path can be incremental:

1. Markdown files and templates.
2. Lightweight validation scripts.
3. A CLI for running workflow steps.
4. An API for creating cases and storing artifacts.
5. A SaaS UI for review, approval, and collaboration.

This order keeps the workflow honest. The UI grows around a process that already works in files. The API wraps behavior that is already visible. The CLI automates steps that have already been reviewed manually.

For AI workflow products, that sequence is practical. It keeps the first version simple, inspectable, and useful before the system becomes larger.

## What Markdown-First Does Not Solve

Markdown-first is not a complete product strategy by itself. It does not provide collaboration controls, authentication, approval routing, notifications, or dashboard views. It also does not prove that the underlying workflow is correct.

What it does provide is a clear starting surface. The team can inspect the artifacts, challenge the assumptions, and decide which parts deserve automation. That is why I see Markdown-first work as a useful discipline for AI workflow products: it forces the process to become legible before the product becomes polished.

When the workflow is legible, later engineering decisions become easier. A CLI can run known steps. An API can expose known resources. A UI can display known artifacts. The product grows from a workflow that already has a shape.
