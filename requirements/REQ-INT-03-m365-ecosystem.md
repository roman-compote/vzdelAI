---
title: Microsoft 365 Ecosystem Integration
req-id: REQ-INT-03
status: draft
priority: must
category: integration
source-section: "5.7"
source-type: extracted
activity:
  - 1
  - 2
  - 3
partners:
  - aricoma
  - comtec
  - compote
milestone: M4
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/integration
  - platform/sharepoint
  - platform/entra-id
---

# REQ-INT-03: Microsoft 365 Ecosystem Integration

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 5.7

## Description

The system shall integrate with the broader Microsoft 365 ecosystem including SharePoint and OneDrive for document storage and knowledge base access, Microsoft Entra ID for identity management and access control, Power Automate for workflow automation, and Power BI / Microsoft Fabric for analytics and reporting.

## Key Capabilities

- **SharePoint/OneDrive:** Read/write access to teacher knowledge bases, document libraries, and shared resources
- **Entra ID:** Authentication, authorization, role-based access control, user profile data
- **Power Automate:** Workflow automation for content approval, notification routing, scheduled tasks
- **Power BI / Fabric:** Dashboard embedding, data pipeline integration, analytics visualization
- **Microsoft Graph API:** Unified access to M365 services (calendar, mail, files, people)

## Acceptance Criteria

- [ ] Teachers can designate SharePoint/OneDrive folders as AI knowledge base sources
- [ ] Entra ID roles (student, teacher, admin) enforced across all system components
- [ ] At least 2 Power Automate workflows operational (e.g., content approval, notification)
- [ ] Power BI dashboards embedded and accessible via Teams and web interface
- [ ] Microsoft Graph API used for unified M365 data access

## Dependencies

- [[REQ-NFR-04-scalability-security|REQ-NFR-04]]: Azure AD / Entra ID configuration
- [[REQ-NFR-01-gdpr-data-protection|REQ-NFR-01]]: Data access scoping per GDPR

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §5.7 |
| **Activity** | 1 (AI Assistant), 2 (Teams Integration), 3 (RAG Pipeline) |
| **Partner** | Aricoma, COMTEC, COMPOTE |
| **Milestone** | M4 (integrated system) |

> [!question] Open Questions
> - What Microsoft 365 license tier is available at UNIZA (E3, E5)?
> - What SharePoint site structure exists for faculty document management?
> - Are there existing Power Automate flows that should be integrated?
> - What Graph API permissions will be required (delegated vs. application)?
