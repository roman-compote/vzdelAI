---
title: Accessibility (WCAG 2.1)
req-id: REQ-NFR-03
status: draft
priority: must
category: non-functional
source-section: "16"
source-type: extracted
activity:
  - 2
partners:
  - comtec
milestone: M4
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/requirement
  - topic/ux
  - topic/compliance
---

# REQ-NFR-03: Accessibility (WCAG 2.1)

> [!info] Source
> [[VzdelAI_Project_Description]] — Section 16

## Description

The system shall comply with WCAG 2.1 accessibility standards at minimum AA level across all user-facing interfaces. This includes the web application, Teams bot interactions, and generated educational materials. The system shall support online participation, barrier-free operation, and assistive technology compatibility.

## Key Capabilities

- WCAG 2.1 Level AA compliance for all web interfaces
- Keyboard navigation support across all interactive elements
- Screen reader compatibility for all user-facing content
- Sufficient color contrast ratios per WCAG guidelines
- Alternative text for all visual content (images, diagrams, charts)
- Accessible generated materials (tagged PDFs, accessible PPTX)
- Support for assistive technologies (screen magnifiers, voice control)

## Acceptance Criteria

- [ ] WCAG 2.1 Level AA compliance verified via automated tools (axe, Lighthouse)
- [ ] Manual accessibility testing completed with assistive technology users
- [ ] All generated materials meet accessibility standards (tagged PDFs, alt text)
- [ ] Keyboard navigation functional for all core workflows
- [ ] No critical accessibility issues in automated scan results

## Dependencies

- [[REQ-INT-01-teams-bot|REQ-INT-01]]: Teams bot must produce accessible message formats
- [[REQ-TECH-05-content-transformation|REQ-TECH-05]]: Generated content must meet accessibility standards

## Traceability

| Field | Value |
|-------|-------|
| **Source** | Project Description §16 |
| **Activity** | 2 (MS Teams Integration — primary UI) |
| **Partner** | COMTEC |
| **Milestone** | M4 (integrated system) |

> [!question] Open Questions
> - Is WCAG 2.1 AA sufficient or should AAA be targeted for specific features?
> - How will accessibility of AI-generated content be validated automatically?
> - What assistive technologies are most commonly used at UNIZA?
