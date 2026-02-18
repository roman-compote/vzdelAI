---
title: Requirements Review — Consistency, Completeness & Gaps
status: active
author: research-team
created: 2026-02-18
updated: 2026-02-18
tags:
  - type/planning
  - type/review
---

# Requirements Review — Consistency, Completeness & Gaps

> [!info] Scope
> Review of all 28 requirement documents in `requirements/` against the [[_requirement-template]], the [[requirements-index]], cross-document consistency, and the [[VzdelAI_Project_Description]] (sections 4–9, 16).

## 1. Structural Consistency

**Overall verdict:** All 28 documents follow the template structure consistently.

- YAML frontmatter with all required fields present
- Description, Key Capabilities, Acceptance Criteria, Dependencies, Traceability, Open Questions sections complete
- Consistent use of `[[wikilinks]]` for cross-references
- Consistent callout syntax (`> [!info]`, `> [!question]`)
- All marked `status: draft`, all dated `2026-02-18`

### Minor Issue: Subcategory Field

The [[_requirement-template]] includes a `subcategory` field, but TECH, INT, and NFR requirements omit it. This is reasonable (subcategory only applies to functional requirements) but should be documented as intentional in the template or in [[planning/conventions-tags-frontmatter]].

- [ ] Document subcategory field usage convention

---

## 2. Dependency & Milestone Conflicts

### Critical: Temporal Dependency Violation

| Requirement | Milestone | Depends On | Dep. Milestone | Problem |
|---|---|---|---|---|
| [[REQ-FUNC-S01-personalized-exam-preparation\|REQ-FUNC-S01]] | **M4** | [[REQ-FUNC-T03-student-progress-monitoring\|REQ-FUNC-T03]] | **M5** | S01 depends on something delivered *later* |

REQ-FUNC-S01 needs student progress data from T03 for personalization, but T03 is scheduled a full milestone later. Either S01's dependency should be relaxed (initial version without personalization) or T03 should be moved to M4.

- [ ] Resolve S01→T03 milestone conflict

### Potential Concern: M3 Bottleneck

Seven requirements target M3 (all 5 TECH + [[REQ-NFR-04-scalability-security|REQ-NFR-04]] + [[REQ-FUNC-T01-automated-material-generation|REQ-FUNC-T01]]). This is a very heavy milestone. If any TECH requirement slips, it cascades to the 10+ requirements at M4 that depend on them.

- [ ] Assess M3 load and consider phasing TECH requirements

---

## 3. Overlapping Scope

### OCR Processing Defined in Two Places

- [[REQ-TECH-03-input-processing|REQ-TECH-03]] (Input Processing): OCR for incoming user inputs (scanned docs, handwritten notes)
- [[REQ-TECH-04-rag-pipeline|REQ-TECH-04]] (RAG Pipeline): OCR as part of content preparation for the knowledge base

These are likely distinct use cases (real-time input vs. batch ingestion), but the boundary isn't explicit. Risk of duplicated effort or architectural confusion between Aricoma (TECH-03) and COMPOTE (TECH-04).

- [ ] Add scope boundary notes to both TECH-03 and TECH-04

---

## 4. Missing Requirements

> [!info] Source type classification
> Each gap below is annotated with its expected `source-type` when created:
> - **extracted** — content exists in the [[VzdelAI_Project_Description]] and can be traced to a specific section
> - **derived** — inferred from the project description or from dependencies between extracted requirements
> - **stakeholder** — will emerge from team discussions, research, or design decisions

### 4a. No Web Application Requirement — HIGH | `derived`

The project commits to a "Dual interface: MS Teams bot (primary) + web application (full dashboards)". [[REQ-INT-01-teams-bot|REQ-INT-01]] covers Teams. Power BI dashboards are mentioned in [[REQ-FUNC-T03-student-progress-monitoring|T03]], [[REQ-FUNC-A02-teaching-optimization-analytics|A02]], and [[REQ-INT-03-m365-ecosystem|INT-03]], but there is **no dedicated requirement** for the web application/dashboard interface itself — its authentication, UI framework, hosting, or feature scope.

The project description mentions "dual interface" (§5.2) but does not specify the web application in detail — this is a derived requirement.

- [ ] Create `REQ-INT-04` — Web Dashboard Application (`source-type: derived`)

### 4b. Activity 5 Almost Entirely Unmapped — CRITICAL | `extracted`

Activity 5 (Testing & Deployment Methodology, UNIZA, 460 person-months) is a major project activity, but only [[REQ-NFR-01-gdpr-data-protection|REQ-NFR-01]] and [[REQ-NFR-02-eu-ai-act|REQ-NFR-02]] reference it — and only for compliance aspects. The core Activity 5 scope is missing:

| Missing Scope | Description | Source |
|---|---|---|
| **Behavior definition & tuning** | Model parameter tuning (temperature, formality, sentiment, language variants), didactic principles, Socratic method implementation | §6-Act5, §5.2 |
| **Pilot testing methodology** | User selection criteria, feedback collection, iterative improvement cycles, A/B testing | §6-Act5, §9 |
| **Deployment methodology** | Comprehensive deployment guides, training programs for other faculties, institutional adoption framework | §6-Act5 |

All three are described in the project description and can be **extracted** directly.

- [ ] Create `REQ-PROCESS-01` — Behavior Definition and Tuning (`source-type: extracted`)
- [ ] Create `REQ-PROCESS-02` — Pilot Testing Methodology (`source-type: extracted`)
- [ ] Create `REQ-PROCESS-03` — Deployment Methodology (`source-type: extracted`)
- [ ] Or: decide these are project management artifacts and document that decision

### 4c. No M1 Milestone Coverage — MEDIUM | `extracted`

M1 ("Completed requirements analysis and input data specification", Q2/2026) is not referenced by any requirement document. If M1 deliverables include system outputs (e.g., a requirements management tool, data specification schema), they should be captured. If M1 is purely a project management milestone, that decision should be documented. M1 is defined in §7 of the project description.

- [ ] Document M1 milestone scope decision

### 4d. No Notification/Alerting System Requirement — MEDIUM | `derived`

Multiple requirements mention notifications in passing:

- [[REQ-FUNC-T03-student-progress-monitoring|T03]]: "Proactive alerts when students fall below thresholds"
- [[REQ-FUNC-S03-study-planning-scheduling|S03]]: "Automatic reminders for deadlines and study sessions"
- [[REQ-FUNC-A01-automated-information-administration|A01]]: "Grant call notifications"

But there's no requirement defining the notification infrastructure — delivery channels, preferences, frequency, opt-out. These are spread across 3+ requirements with no single owner. This is derived from the pattern of multiple extracted requirements needing notification capabilities.

- [ ] Create `REQ-TECH-06` — Notification Service (`source-type: derived`), or assign notification ownership within each functional requirement

### 4e. No Academic Integrity Safeguard Requirement — MEDIUM | `stakeholder`

[[REQ-FUNC-T02-assessment-correction-support|REQ-FUNC-T02]] mentions AI-generated content detection and [[REQ-FUNC-S02-homework-paper-assistance|REQ-FUNC-S02]] mentions "clear boundaries to prevent over-reliance", but there's no unified requirement for academic integrity policy enforcement — usage limits, honesty declarations, audit trails for student-AI interactions, teacher visibility into AI assistance levels.

The project description does not specify academic integrity policies — this will need to emerge from stakeholder discussions with UNIZA faculty.

- [ ] Consider creating a dedicated academic integrity requirement (`source-type: stakeholder`) or adding explicit safeguard sections to T02 and S02

### 4f. No Conversation History / Persistence Requirement — MEDIUM | `derived`

[[REQ-TECH-02-agent-architecture|REQ-TECH-02]] mentions "multi-turn conversation state" and [[REQ-FUNC-T04-interactive-consultations|REQ-FUNC-T04]] mentions "interaction logs available for teacher review", but no requirement defines:

- How long conversation history is retained
- Whether students can access their own history
- Export capabilities
- GDPR implications of storing conversations

This is derived from the combination of TECH-02 (agent state) and NFR-01 (GDPR data retention).

- [ ] Add conversation persistence requirements to TECH-02 or create a dedicated requirement (`source-type: derived`)

### 4g. No Teacher Knowledge Base Management Requirement — LOW-MEDIUM | `derived`

Multiple requirements assume teachers upload and manage materials ([[REQ-FUNC-T01-automated-material-generation|T01]], [[REQ-TECH-04-rag-pipeline|TECH-04]], [[REQ-INT-03-m365-ecosystem|INT-03]]), but no requirement specifies the management interface — organize folders, update/delete documents, see indexing status, manage access permissions.

This is derived from the pattern of multiple extracted requirements assuming a management interface exists.

- [ ] Add knowledge base management capabilities to an existing requirement or create a new one (`source-type: derived`)

---

## 5. Acceptance Criteria Gaps

Some acceptance criteria are **not measurable** or missing thresholds:

| Requirement | Issue |
|---|---|
| [[REQ-FUNC-T01-automated-material-generation\|T01]] | "Generated content passes quality review" — no defined quality metric |
| [[REQ-FUNC-T02-assessment-correction-support\|T02]] | "Within a reasonable timeframe" — no specific SLA |
| [[REQ-FUNC-T04-interactive-consultations\|T04]] | "Verified accuracy above a defined threshold" — threshold undefined |
| [[REQ-FUNC-S02-homework-paper-assistance\|S02]] | "Within minutes" — vague; should specify e.g., <60 seconds |
| [[REQ-FUNC-S05-step-by-step-problem-solving\|S05]] | "Explanation depth adapts" — no measurable criterion for adaptation |
| [[REQ-NFR-04-scalability-security\|NFR-04]] | "No critical or high-severity findings" — which security framework? |

- [ ] Add specific, measurable thresholds to each (even placeholder values to be refined during M1/M2)

---

## 6. Quantitative Targets (§9) — Scattered, Not Centralized

The [[VzdelAI_Project_Description]] defines specific pilot targets. These appear inconsistently across requirements:

| Target | Where Referenced | Status |
|---|---|---|
| 250+ students engaged | [[REQ-FUNC-T03-student-progress-monitoring\|T03]], [[REQ-FUNC-S01-personalized-exam-preparation\|S01]] | Partially captured |
| 70+ teachers engaged | [[REQ-FUNC-T02-assessment-correction-support\|T02]] | Partially captured |
| 900+ materials analyzed | [[REQ-FUNC-T01-automated-material-generation\|T01]] | Captured in one place |
| 1,500+ materials generated | [[REQ-FUNC-T01-automated-material-generation\|T01]], [[REQ-TECH-05-content-transformation\|TECH-05]] | Duplicated |
| User satisfaction (Likert) | [[REQ-FUNC-T04-interactive-consultations\|T04]], [[REQ-FUNC-S01-personalized-exam-preparation\|S01]], [[REQ-INT-01-teams-bot\|INT-01]] | Scattered |
| International student metrics | [[REQ-FUNC-I01-international-student-support\|I01]] | Captured |

- [ ] Create `REQ-NFR-05` — Pilot Success Metrics, or add a cross-reference table in the [[requirements-index]]

---

## 7. Activity Coverage Summary

| Activity | Partner | Requirements Mapped | Coverage |
|---|---|---|---|
| 1 — AI Assistant | Aricoma | 18 requirements | Full |
| 2 — Teams Integration | COMTEC | 8 requirements | Full |
| 3 — RAG & Content | COMPOTE | 10 requirements | Full |
| 4 — Analytics | ESMO | 4 requirements | Adequate |
| 5 — Testing & Deployment | UNIZA | 2 requirements (compliance only) | **~5% — Critical gap** |
| 6 — Scientific Publishing | UNIZA | 0 requirements | **0% — Intentional exclusion, undocumented** |

- [ ] Create Activity 5 requirements (see §4b above)
- [ ] Document Activity 6 exclusion rationale in the [[requirements-index]] (currently only a partial note about deliverables)

---

## 8. Priority Distribution

| Priority | Count | Requirements |
|---|---|---|
| **must** | 19 | All TECH (5), all INT (3), all NFR (4), T01–T04, S01, S02, S05 |
| **should** | 6 | T05, T06, S03, S06, A02, I01 |
| **could** | 3 | S04, A01, E01 |

19 "must" requirements is ambitious for the timeline. Consider whether all are truly MVP-critical or if some could be downgraded to "should" for the pilot (e.g., [[REQ-TECH-03-input-processing|TECH-03]]'s OCR/Speech-to-Text could start as "should" with text-only input for MVP).

- [ ] Review "must" requirements and consider if any can be phased

---

## 9. Recommended Actions (Priority Order)

| # | Action | Priority | Section |
|---|---|---|---|
| 1 | Fix the S01→T03 milestone conflict | Critical | §2 |
| 2 | Create Activity 5 requirements (or document exclusion) | Critical | §4b |
| 3 | Create `REQ-INT-04` for web dashboard application | High | §4a |
| 4 | Clarify TECH-03/TECH-04 OCR boundary with scope notes | High | §3 |
| 5 | Sharpen vague acceptance criteria with measurable thresholds | High | §5 |
| 6 | Consolidate pilot success metrics into one place | Medium | §6 |
| 7 | Add notification infrastructure requirement or assign ownership | Medium | §4d |
| 8 | Document M1 milestone scope decision | Medium | §4c |
| 9 | Document Activity 6 exclusion rationale in the index | Medium | §7 |
| 10 | Add conversation persistence requirements | Medium | §4f |
| 11 | Add academic integrity safeguard requirements | Medium | §4e |
| 12 | Add teacher knowledge base management requirements | Low | §4g |
| 13 | Review "must" count and consider phasing | Low | §8 |

---

> [!tip] Next Steps
> Work through the action items above in priority order. Each checkbox can be ticked off as the issue is resolved, making this document a living tracker for requirements maturity.
