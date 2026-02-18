---
title: LLM Foundation and Fine-Tuning
req-id: REQ-TECH-01
status: draft
priority: must
category: technical
source-section: "5.1, 5.2"
source-type: extracted
activity:
  - 1
partners:
  - aricoma
milestone: M3
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/llm
  - platform/azure-openai
---

# REQ-TECH-01: LLM Foundation and Fine-Tuning

> [!info] Source
> [[VzdelAI_Project_Description]] — Sections 5.1, 5.2

## Description

The system shall utilize Large Language Models from the Microsoft Azure AI Model Catalog as its AI foundation. Models shall be fine-tuned for the Slovak academic context, incorporating Slovak terminology, educational curricula, and pedagogical conventions to ensure outputs are content-correct and adapted to the Slovak educational environment.

## Key Capabilities

- Deploy and manage LLMs from Azure AI Model Catalog
- Fine-tune models with Slovak academic terminology and naming conventions
- Incorporate educational materials, textbooks, and methodological guides into training data
- Ensure high availability and scalability via Azure cloud infrastructure
- Support hybrid strategy: Azure OpenAI for production, local models (Ollama) for development and privacy-sensitive scenarios

## Acceptance Criteria

- [ ] At least one LLM deployed and operational on Azure AI Model Catalog
- [ ] Fine-tuned model demonstrates improved accuracy on Slovak academic content vs. base model
- [ ] Model outputs use correct Slovak academic terminology and conventions
- [ ] Adapted AI models achieve TRL 4 — experimental validation in relevant environment (§2.1)
- [ ] Model response latency within acceptable thresholds for interactive use
- [ ] Local development environment with Ollama available for privacy-sensitive testing

## Dependencies

- [[REQ-NFR-04-scalability-security|REQ-NFR-04]]: Azure infrastructure provisioning
- [[REQ-NFR-01-gdpr-data-protection|REQ-NFR-01]]: Training data handling must comply with GDPR

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §5.1, §5.2, §2.1 |
| **Activity** | 1 (AI Assistant Design & Development) |
| **Partner** | Aricoma |
| **Milestone** | M3 (fine-tuned AI models available) |

> [!question] Open Questions
> - Which specific models from Azure AI Model Catalog will be evaluated?
> - What is the minimum dataset size for effective Slovak academic fine-tuning?
> - How will fine-tuning effectiveness be benchmarked (specific evaluation metrics)?
