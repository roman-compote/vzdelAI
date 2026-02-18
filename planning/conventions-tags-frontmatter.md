---
title: Tags & Frontmatter Conventions
status: draft
updated: 2026-02-18
---

# Tags & Frontmatter Conventions

> [!note]
> This is a living document. Update as the project evolves and new categories emerge.

## Standard YAML Frontmatter

Every research and planning document should include this frontmatter block:

```yaml
---
title: "Document Title"
status: draft | review | final | archived
author: name-or-team
created: YYYY-MM-DD
updated: YYYY-MM-DD
activity: 1-6         # project activity number (see below)
partners: []          # relevant consortium partners
tags: []              # see tag taxonomy below
---
```

### Field Descriptions

| Field | Required | Values | Description |
|-------|----------|--------|-------------|
| `title` | Yes | free text | Human-readable document title |
| `status` | Yes | `draft` / `review` / `final` / `archived` | Document lifecycle stage |
| `author` | Yes | name or team | Primary author or responsible team |
| `created` | Yes | `YYYY-MM-DD` | Date of initial creation |
| `updated` | Yes | `YYYY-MM-DD` | Date of last substantive update |
| `activity` | No | `1`–`6` | Project activity number (see table below) |
| `partners` | No | list | Consortium partners relevant to this doc |
| `tags` | Yes | list | Tags from taxonomy below |

### Activity Numbers

| # | Activity | Partner |
|---|----------|---------|
| 1 | AI Assistant Design & Development | Aricoma |
| 2 | MS Teams Integration | COMTEC |
| 3 | RAG Pipeline & Content Generation | COMPOTE |
| 4 | Predictive Analytics & Visualization | ESMO |
| 5 | Testing & Deployment Methodology | UNIZA |
| 6 | Scientific Publishing | UNIZA |

### Partner Identifiers

Use these exact values in `partners` field:
- `uniza` — University of Žilina (PEDaS)
- `aricoma` — Aricoma Systems
- `compote` — COMPOTE
- `esmo` — ESMO Žilina
- `comtec` — COMTEC

## Tag Taxonomy

Tags use hierarchical namespacing with `/` separator.

### Topic Tags

| Tag | Use for |
|-----|---------|
| `topic/ai-assistant` | Core AI assistant functionality |
| `topic/rag` | RAG pipeline, retrieval, embeddings |
| `topic/llm` | LLM selection, fine-tuning, prompting |
| `topic/analytics` | Predictive analytics, learning analytics |
| `topic/integration` | System integration (Teams, Moodle, M365) |
| `topic/compliance` | EU AI Act, GDPR, data protection |
| `topic/pedagogy` | Teaching methods, Socratic method, adaptive learning |
| `topic/ux` | User experience, interface design |
| `topic/security` | Authentication, authorization, data sovereignty |
| `topic/infrastructure` | Cloud architecture, deployment, DevOps |

### Platform Tags

| Tag | Use for |
|-----|---------|
| `platform/azure` | Azure services (general) |
| `platform/azure-openai` | Azure OpenAI Service |
| `platform/azure-ai-search` | Azure Cognitive Search / AI Search |
| `platform/teams` | Microsoft Teams |
| `platform/moodle` | Moodle LMS |
| `platform/entra-id` | Microsoft Entra ID (auth) |
| `platform/power-bi` | Power BI dashboards |
| `platform/sharepoint` | SharePoint / OneDrive |

### Document Type Tags

| Tag | Use for |
|-----|---------|
| `type/research` | Research & analysis documents |
| `type/planning` | Implementation planning |
| `type/architecture` | Technical architecture decisions |
| `type/literature` | Literature review, paper notes |
| `type/decision` | Architecture Decision Records (ADRs) |
| `type/meeting` | Meeting notes |
| `type/specification` | Technical specifications |
| `type/requirement` | System requirements extracted from project description |

### Status Tags (supplement frontmatter `status`)

| Tag | Use for |
|-----|---------|
| `needs/re-research` | Document needs re-research (e.g., stack realignment) |
| `needs/review` | Awaiting peer review |
| `needs/update` | Content is outdated, needs refresh |

## Dataview Query Examples

List all draft documents:
```dataview
TABLE title, author, updated
FROM ""
WHERE status = "draft"
SORT updated DESC
```

All documents for Activity 3 (RAG Pipeline):
```dataview
TABLE title, status, partners
FROM ""
WHERE activity = 3
SORT updated DESC
```

Documents needing re-research:
```dataview
LIST
FROM #needs/re-research
```

## Conventions for Inline Fields

When using Dataview inline fields within document body:

```markdown
Reviewed by:: John Doe
Decision:: Approved
Due date:: 2026-03-15
```

Use `::` syntax for inline fields that Dataview can query.

## Requirement Document Conventions

Requirement documents live in `requirements/` and extend the standard frontmatter with additional fields.

### Naming Convention

- **Pattern:** `REQ-{CATEGORY}-{ID}-{slug}.md`
- **Examples:**
  - `REQ-FUNC-T01-automated-material-generation.md`
  - `REQ-TECH-01-llm-foundation.md`
  - `REQ-INT-02-moodle-integration.md`
  - `REQ-NFR-01-gdpr-data-protection.md`

### Category Prefixes

| Prefix | Category |
|--------|----------|
| `REQ-FUNC-Txx` | Functional — Teacher |
| `REQ-FUNC-Sxx` | Functional — Student |
| `REQ-FUNC-Ixx` | Functional — International |
| `REQ-FUNC-Axx` | Functional — Administration |
| `REQ-FUNC-Exx` | Functional — External |
| `REQ-TECH-xx` | Technical |
| `REQ-INT-xx` | Integration |
| `REQ-NFR-xx` | Non-Functional |

### Requirement-Specific Frontmatter Fields

These fields are used **in addition to** the standard frontmatter fields:

| Field | Required | Values | Description |
|-------|----------|--------|-------------|
| `req-id` | Yes | `REQ-FUNC-T01`, etc. | Unique requirement identifier |
| `priority` | Yes | `must` / `should` / `could` / `wont` | MoSCoW priority |
| `category` | Yes | `functional` / `technical` / `integration` / `non-functional` | Requirement category |
| `subcategory` | No | `teacher` / `student` / `international` / `admin` / `external` | For functional requirements |
| `source-section` | Yes | `"5.1"`, `"8.1"`, etc. | Section reference in project description |
| `milestone` | No | `M1`–`M6` | Related project milestone |

### Requirement Dataview Query Examples

All requirements by priority:
```dataview
TABLE req-id, title, priority, category
FROM "requirements"
WHERE contains(tags, "type/requirement")
SORT choice(priority = "must", 1, choice(priority = "should", 2, choice(priority = "could", 3, 4))) ASC
```

Must-have requirements only:
```dataview
TABLE req-id, title, category, activity
FROM "requirements"
WHERE contains(tags, "type/requirement") AND priority = "must"
SORT req-id ASC
```

Requirements by category:
```dataview
TABLE req-id, title, priority
FROM "requirements"
WHERE contains(tags, "type/requirement")
GROUP BY category
```

Requirements for a specific activity/partner:
```dataview
TABLE req-id, title, priority, partners
FROM "requirements"
WHERE contains(tags, "type/requirement") AND contains(activity, 2)
SORT req-id ASC
```
