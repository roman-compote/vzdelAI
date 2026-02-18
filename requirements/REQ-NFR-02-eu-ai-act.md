---
title: EU AI Act Compliance
req-id: REQ-NFR-02
status: draft
priority: must
category: non-functional
source-section: "16"
source-type: extracted
activity:
  - 1
  - 5
partners:
  - aricoma
  - uniza
milestone: M2
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/compliance
---

# REQ-NFR-02: EU AI Act Compliance

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 16; [[07-regulatory-compliance]]

## Description

The system shall comply with the EU AI Act (Regulation 2024/1689). Educational AI systems are classified as **high-risk under Annex III** (access to and admission to educational and vocational training institutions; evaluation of learning outcomes). The compliance deadline is **2 August 2026**. The system must implement all high-risk AI requirements including risk management, data governance, transparency, human oversight, and technical documentation.

## Key Capabilities

- Risk management system covering the full AI lifecycle
- Data governance: training data quality, bias detection, representativeness documentation
- Transparency: users informed they are interacting with an AI system
- Human oversight: mechanisms for teacher override and intervention
- Technical documentation: model cards, system architecture, testing reports
- Accuracy, robustness, and cybersecurity measures
- Registration in the EU AI database (when available)
- Conformity assessment procedures

## Acceptance Criteria

- [ ] Risk management system documented and operational before 2 August 2026 deadline
- [ ] Users clearly informed they are interacting with an AI system at first contact
- [ ] Human oversight mechanisms allow teachers to override/correct AI outputs
- [ ] Technical documentation complete (model cards, data sheets, architecture docs)
- [ ] Bias detection and mitigation measures implemented for training data
- [ ] System registered in EU AI database (when operational)
- [ ] Conformity assessment completed or in progress by deadline

## Dependencies

- [[REQ-NFR-01-gdpr-data-protection|REQ-NFR-01]]: GDPR compliance as prerequisite for AI Act data governance
- [[REQ-TECH-01-llm-foundation|REQ-TECH-01]]: Model documentation and transparency requirements

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §16, EU AI Act (Regulation 2024/1689), [[07-regulatory-compliance]] |
| **Activity** | 1 (AI Assistant), 5 (Testing & Deployment) |
| **Partner** | Aricoma, UNIZA |
| **Milestone** | M2 (architecture must include compliance-by-design) |

> [!question] Open Questions
> - Which conformity assessment path applies (self-assessment vs. third-party)?
> - What is the timeline for EU AI database registration availability?
> - How will ongoing compliance monitoring be implemented post-deployment?
> - Should a dedicated AI ethics board be established for the project?
