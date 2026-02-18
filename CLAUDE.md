# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

VzdelAI is a research project at the University of Žilina (Faculty of Operation and Economics of Transport and Communications — PEDaS) developing an AI-powered digital assistant for higher education. The repository is currently in the **research and planning phase** (pre-implementation) — there is no source code, build system, or tests yet.

The project targets personalized AI support for teachers and students, integrating with Microsoft Teams and Moodle LMS, with a focus on Economics and Finance courses.

**Project period:** 36 months (Q1/2026 – Q4/2028)
**Consortium:** University of Žilina + 4 industry partners (Aricoma, COMPOTE, ESMO, COMTEC)

## Authoring Environment

This repository is an **Obsidian vault**. All documentation is authored and viewed in Obsidian. When generating or editing Markdown files, use Obsidian-compatible syntax and features:

- **Language:** All research documents are written in **English** (enables RAG/semantic search without Slovak embeddings). Source material and web research may be in Slovak.
- **Writing style:** Technical brief — concise, structured, factual. Use headers, bullet points, and tables for scannability.
- **Internal links:** Use `[[wikilinks]]` for cross-referencing between documents
- **Callouts:** Use Obsidian callout syntax (`> [!note]`, `> [!warning]`, `> [!tip]`, etc.)
- **Bases (datatables):** Obsidian Bases is enabled — use for structured data views and tables where appropriate
- **Dataview:** Use for querying across documents, dynamic tables, inline fields, and metadata-driven views
- **YAML frontmatter:** Use for document metadata — see [[planning/conventions-tags-frontmatter]] for standard fields and tags
- **Linter:** Obsidian Linter enforces consistent formatting and frontmatter structure — generated Markdown should conform to vault conventions
- **Templater / QuickAdd:** Available for standardized document creation workflows with variables
- **Advanced Tables:** Spreadsheet-like table editing enabled — tables are widely used in research docs
- **Omnisearch:** Full-text relevance-ranked search with PDF indexing
- **Zotero Integration:** Citation import and PDF annotation via `obsidian-zotero-desktop-connector`
- **Enhancing Export:** Pandoc-based export to DOCX, LaTeX, PDF for deliverables and papers
- **Tag Wrangler:** Tag rename/merge/reorganize support — see [[planning/conventions-tags-frontmatter]] for tag taxonomy
- **Diagrams:**
  - **Mermaid** (built-in) — use for simple diagrams (flowcharts, sequence diagrams, basic architecture)
  - **PlantUML** (plugin installed) — use for complex diagrams (detailed component diagrams, class diagrams, deployment architectures)
  - **Excalidraw** (plugin installed) — use for informal sketches, architecture brainstorming, visual planning
- **Canvas:** Available for visual mapping and brainstorming

For the full plugin list and selection guide, see [[planning/obsidian-plugins]].

### Diagram Guidelines

Use ` ```mermaid ` code blocks for simple diagrams:
- Flowcharts, sequence diagrams, Gantt charts, simple architecture overviews

Use ` ```plantuml ` code blocks for complex diagrams:
- Detailed system architecture, deployment diagrams, complex component relationships, UML class/activity diagrams

Use Excalidraw for informal/visual work:
- Architecture brainstorming, freehand sketches, visual planning sessions

## Repository Structure

- `_input/` — Project description document (main spec, in Slovak/English)
- `_source/` — Original source documents (Word format)
- `research/` — Research documents (01, 02, 04, 06, 07, 08 active; 03, 05, 09 archived)
- `planning/` — Implementation planning, vault conventions, plugin recommendations
- `_archive/` — Research docs pending re-research with Microsoft-native stack (03, 05, 09, component-mapping)
- `.obsidian/` — Obsidian vault configuration (documentation is authored/viewed as an Obsidian vault)

## Technical Architecture (per Project Description)

The project description commits to a **Microsoft-native stack**:

- **Cloud Platform:** Microsoft Azure
- **AI Models:** Azure AI Services, Azure AI Model Catalog, Azure OpenAI
- **Vector Database:** Azure Cognitive Search
- **Identity Management:** Microsoft Entra ID (Azure AD)
- **Bot Framework:** Azure Bot Services, MS Teams Bot Framework
- **Collaboration:** Microsoft Teams, Microsoft 365
- **Content Management:** SharePoint, OneDrive, Moodle
- **Automation:** Power Automate
- **Analytics/BI:** Power BI, Microsoft Fabric
- **DevOps:** Azure DevOps tools
- **LMS Integration:** LTI 1.3 (Moodle), xAPI for analytics

**Note:** Previous research (archived) recommended an open-source stack (FastAPI, pgvector, Next.js, LlamaIndex). This diverged from the project description's commitments. New research should align with the Microsoft-native stack above, while evaluating where open-source components may complement it.

## Key Design Principles

- **4-layer prompting system:** global context → instructional logic (Socratic method) → adaptive variables (student model) → post-interaction (reflection)
- **Hybrid LLM strategy:** Azure OpenAI for production; local models (Ollama) for development and privacy-sensitive scenarios
- **EU AI Act compliance:** educational AI is classified as high-risk under Annex III; compliance deadline is **2 August 2026**; GDPR data sovereignty required
- **Dual interface:** MS Teams bot (primary) + web application (full dashboards)

## Research Documents Reference

Active research documents:
- `research/01-executive-summary.md` — high-level overview and key findings
- `research/02-platform-landscape.md` — existing AI education platforms analysis
- `research/04-ms-teams-integration.md` — Microsoft ecosystem integration
- `research/06-academic-research.md` — papers, case studies, CEE projects
- `research/07-regulatory-compliance.md` — EU AI Act, GDPR, Slovakia context
- `research/08-challenges-risks.md` — challenges, risks, lessons learned

Archived (pending re-research with Microsoft stack):
- `_archive/03-technical-architecture.md`
- `_archive/05-open-source-tools.md`
- `_archive/09-recommendations.md`
- `_archive/component-mapping.md`

## Project Activities & Partner Responsibilities

| Activity | Partner | Scope |
|----------|---------|-------|
| 1. AI Assistant Design & Development | Aricoma Systems | Core AI assistant, fine-tuning, implementation |
| 2. MS Teams Integration | COMTEC | Teams bot, M365 integration, EntraID auth |
| 3. RAG Pipeline & Content Generation | COMPOTE | Document processing, vector DB, output generation |
| 4. Predictive Analytics & Visualization | ESMO Žilina | Analytics, Power BI dashboards, student prediction |
| 5. Testing & Deployment Methodology | UNIZA (PEDaS) | Behavior design, pilot testing, deployment guides |
| 6. Scientific Publishing | UNIZA (PEDaS) | Publications, conference, courses, theses |
