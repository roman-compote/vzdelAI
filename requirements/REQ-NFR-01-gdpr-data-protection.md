---
title: GDPR and Data Protection
req-id: REQ-NFR-01
status: draft
priority: must
category: non-functional
source-section: "5.5, 16"
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
  - topic/security
---

# REQ-NFR-01: GDPR and Data Protection

> [!info] Source
> [[VzdelAI_Project_Description]] — Sections 5.5, 16

## Description

The system shall comply with the General Data Protection Regulation (GDPR) across all components. This includes data sovereignty within the EU, pseudonymization of personal data in analytics, role-based access control at the document and data level, and explicit consent management for data processing. All data storage and processing shall occur within EU Azure regions.

## Key Capabilities

- EU data residency: all data stored and processed in EU Azure regions
- Pseudonymization of student data in analytics and reporting pipelines
- Role-based access control (RBAC) enforced at document, chunk, and feature level
- Consent management: explicit consent collection and withdrawal support
- Data minimization: collect only data necessary for the stated purpose
- Right to erasure: ability to delete all personal data on request
- Data processing agreements (DPA) with all partners and sub-processors
- Audit logging for all personal data access and processing

## Acceptance Criteria

- [ ] All data storage located in EU Azure regions (verified by architecture review)
- [ ] Pseudonymization applied to all student data in analytics dashboards
- [ ] RBAC enforced — users can only access data appropriate to their role
- [ ] Consent collection implemented for all personal data processing
- [ ] Right to erasure functional — student data deletable within defined timeframe
- [ ] Audit logs capture all personal data access events
- [ ] DPA executed with all consortium partners

## Dependencies

- [[REQ-NFR-04-scalability-security|REQ-NFR-04]]: Infrastructure must support EU-only deployment
- [[REQ-INT-03-m365-ecosystem|REQ-INT-03]]: Entra ID for RBAC implementation

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §5.5, §16, GDPR |
| **Activity** | 1 (AI Assistant), 5 (Testing & Deployment) |
| **Partner** | Aricoma, UNIZA |
| **Milestone** | M2 (architecture finalized — GDPR design must be built-in) |

> [!question] Open Questions
> - Who is the Data Protection Officer (DPO) for the project?
> - What is the legal basis for processing student data (consent vs. legitimate interest)?
> - What is the data retention policy (how long are interaction logs kept)?
> - How will cross-border data transfers be handled for multilingual features?
