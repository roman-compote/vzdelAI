# 01 — Executive Summary

> Synthesized key findings from research on AI in education, informing the VzdelAI platform design.

---

## Market Overview

The AI in education market is experiencing explosive growth:

- **Market size:** $6.9 billion (2025) → projected **$41 billion by 2030**
- **CAGR:** 42.83% ([Grand View Research, 2025](https://www.grandviewresearch.com/industry-analysis/artificial-intelligence-in-education-market))
- **Key drivers:** Personalization demand, teacher workload reduction, institutional digital transformation

## Student & Teacher Adoption

- **92% of UK undergraduate students** now use AI tools (2025), up from 66% the prior year ([HEPI/Kortext, 2025](https://www.hepi.ac.uk/reports/student-generative-ai-survey-2025/))
- Teachers using AI weekly report saving **~5.9 hours per week** on administrative and preparation tasks ([Gallup/Walton Family Foundation, 2025](https://news.gallup.com/poll/691967/three-teachers-weekly-saving-six-weeks-year.aspx))
- Primary use cases: content creation, grading assistance, personalized feedback, lesson planning

## Platform Categories

AI education tools fall into several distinct categories:

| Category | Examples | Core Value |
|----------|----------|------------|
| **LLM-Based AI Tutors** | Khanmigo, ChatGPT Edu, Copilot for Education | Conversational learning, Socratic questioning |
| **Adaptive Learning** | Squirrel AI, Century Tech, ALEKS, Carnegie Learning | Personalized learning paths, knowledge gap detection |
| **Content Generation** | Copilot, Moodle AI, various plugins | Automated lesson/quiz/material creation |
| **Assessment & Feedback** | Gradescope, Turnitin | AI-assisted grading, integrity checking |
| **Learning Analytics** | xAPI-based dashboards, institutional tools | Student progress tracking, early warning |

→ *Full analysis:* [02-platform-landscape.md](02-platform-landscape.md)

## Technical Architecture Findings

Research consistently shows a common pattern for effective AI tutoring systems:

1. **RAG (Retrieval-Augmented Generation)** is the dominant approach — LPITutor achieved **94% factual accuracy** with RAG vs. 72% with LLM-only ([PeerJ, 2025](https://doi.org/10.7717/peerj-cs.2289))
2. **Hybrid LLM strategy** is recommended: cloud APIs (GPT-4/5, Claude) for quality; local models (Ollama/LLaMA) for privacy and cost control
3. **Prompt engineering** with pedagogical guardrails (Socratic method, scaffolding) significantly improves educational outcomes
4. **Standard protocols** (LTI, xAPI, SCORM) enable integration with existing LMS infrastructure

→ *Full analysis:* [[03-technical-architecture]]

## Regulatory Landscape

**EU AI Act** classifies educational AI systems as **HIGH-RISK**, imposing significant compliance obligations:

- Risk management systems, data governance, technical documentation
- Human oversight requirements and event logging
- Timeline: high-risk rules for Annex III standalone systems (incl. education) effective **August 2026**
- Universities developing AI tools are classified as **high-risk AI system providers**

**Slovakia** has launched a national **"Responsible Use of AI in Education" plan (2025–2027)**:
- AI integration into curricula from the 2026/2027 school year
- AI Competence Centres at selected universities (2026–2029)
- Funded through state budget and EU funds

→ *Full analysis:* [07-regulatory-compliance.md](07-regulatory-compliance.md)

## Key Challenges

| Challenge | Severity | Mitigation |
|-----------|----------|------------|
| Academic integrity concerns | High | Clear policies, detection tools, pedagogical design |
| AI hallucination | High | RAG architecture, domain-specific knowledge bases |
| Data privacy (GDPR) | High | Local LLM options, anonymization, DPIA |
| Faculty resistance | Medium | Training, time-saving demonstrations, gradual rollout |
| Over-reliance on AI | Medium | Socratic approach, critical thinking emphasis |
| Equity of access | Medium | Institutional licensing, MS Teams integration |

→ *Full analysis:* [08-challenges-risks.md](08-challenges-risks.md)

## Recommendations for VzdelAI

The top 10 recommendations for VzdelAI platform design:

1. **RAG-based architecture** — proven by LPITutor and Jill Watson research
2. **Hybrid LLM strategy** — cloud for quality, local for privacy/cost
3. **MS Teams as primary channel** with standalone web UI
4. **Moodle/LMS integration** via LTI standard
5. **Pedagogical guardrails** — Socratic approach (Khanmigo pattern)
6. **xAPI for learning analytics** — standardized tracking and reporting
7. **EU AI Act compliance by design** — high-risk category requirements built in
8. **Open-source components** — leverage Open TutorAI and Moodle AI patterns
9. **Teacher tools first** — content generation, assessment, and feedback
10. **Phased rollout** — Faculty PEDaS pilot → university-wide deployment

→ *Full analysis:* [09-recommendations.md](../_archive/09-recommendations.md) *(archived — pending re-research with Microsoft stack)*

---

## References

- Grand View Research. (2025). *Artificial Intelligence in Education Market Report*. https://www.grandviewresearch.com/industry-analysis/artificial-intelligence-in-education-market
- EDUCAUSE. (2025). *Students and AI: Use, Perceptions, and Policy*. https://www.educause.edu/research-and-publications
- McKinsey & Company. (2025). *How AI is transforming education*. https://www.mckinsey.com/industries/education
- European Parliament. (2024). *Regulation (EU) 2024/1689 — EU AI Act*. https://eur-lex.europa.eu/eli/reg/2024/1689
- MŠVVaM SR. (2025). *Plán zodpovedného využívania AI vo vzdelávaní 2025–2027*. https://www.minedu.sk/
