# 06 — Academic Research: Papers, Case Studies & Frameworks

> Key academic papers, effectiveness evidence, pedagogical frameworks, and Central/Eastern European AI education projects relevant to VzdelAI.

---

## 1. Key Papers & Systems

### 1.1 LPITutor: RAG + Prompt Engineering for Intelligent Tutoring

**Citation:** Alnawas, A., & Al-Araji, Z. (2025). LPITutor: AI-powered intelligent tutoring system using RAG and prompt engineering. *PeerJ Computer Science*, 11, e2289.
**DOI:** [10.7717/peerj-cs.2289](https://doi.org/10.7717/peerj-cs.2289)

| Aspect | Details |
|--------|---------|
| **Problem** | General-purpose LLMs hallucinate and lack domain-specific knowledge for tutoring |
| **Approach** | RAG pipeline with sentence-transformer embeddings + dual-layer prompt engineering |
| **LLM** | GPT-3.5 (no fine-tuning — RAG eliminates the need) |
| **Domain** | Linux Professional Institute (LPI) certification preparation |
| **Results** | 94% factual accuracy (vs. 72% LLM-only); 4.6/5 user satisfaction |
| **Key finding** | RAG is the single most impactful architectural decision — boosted accuracy by 30.5% |
| **Implication for VzdelAI** | Strong evidence that RAG-based architecture is the right choice; fine-tuning is unnecessary when RAG is properly implemented |

### 1.2 Open TutorAI: Open-Source AI-Native Tutoring Platform

**Citation:** Open TutorAI: An Open-Source AI-Native Platform for Immersive Tutoring Experiences. *arXiv preprint*, 2026.
**Source:** [arXiv](https://arxiv.org/)

| Aspect | Details |
|--------|---------|
| **Problem** | Existing AI tutoring tools are closed-source, not customizable, lack pedagogical depth |
| **Approach** | Open-source platform built on OpenWebUI with 4-layer prompting and immersive 3D environment |
| **LLM** | Dual support: Ollama (local) + GPT-4 (cloud) |
| **Key innovation** | 4-layer prompt system (Global → Instructional → Adaptive → Post-interaction) |
| **Key innovation** | Dual knowledge base (institutional curated + user-uploaded) |
| **Implication for VzdelAI** | Provides open-source reference architecture; validates hybrid LLM approach; demonstrates RBAC design for educational context |

### 1.3 Jill Watson: The First AI Teaching Assistant

**Citation:** Goel, A., & Polepeddi, L. (2018). *Jill Watson: A Virtual Teaching Assistant for Online Education.* Georgia Institute of Technology.
**Source:** [DiLab — Georgia Tech](https://dilab.gatech.edu/jill-watson/)

| Aspect | Details |
|--------|---------|
| **Context** | Georgia Tech's OMSCS program (600+ students per section) |
| **Problem** | Overwhelming volume of routine student questions on discussion forums |
| **Approach** | Knowledge-based AI TA trained on course-specific materials and prior Q&A |
| **Performance** | 75–97% accuracy on test sets; students couldn't distinguish from human TAs |
| **Key finding** | **Outperforms general-purpose ChatGPT in classroom settings** due to domain-specific training |
| **Impact** | Enhanced teaching presence (students felt more supported); enhanced social presence (more engagement); freed human TAs for complex questions |
| **Implication for VzdelAI** | Domain-specific, RAG-enhanced systems are superior to generic LLMs for education; course-specific knowledge bases are essential |

### 1.4 AI Agents for Personalized Adaptive Learning

**Citation:** AI agents for personalized adaptive learning: A comprehensive review. *ScienceDirect*, 2025.
**Source:** [ScienceDirect](https://www.sciencedirect.com/)

| Aspect | Details |
|--------|---------|
| **Type** | Systematic literature review |
| **Scope** | AI agent architectures for personalized learning |
| **Key findings** | Multi-agent systems (separate agents for assessment, content selection, feedback) outperform monolithic approaches; agent-based systems better model complex pedagogical strategies |
| **Frameworks reviewed** | Bloom's taxonomy integration, mastery learning, differentiated instruction |
| **Implication for VzdelAI** | Consider multi-agent architecture (e.g., separate assessment agent, tutoring agent, content agent) for better modularity and pedagogical control |

### 1.5 NotebookLM: LLM with RAG for Active Learning

**Citation:** NotebookLM: An AI-First Notebook for Active Learning with RAG. *arXiv preprint*, 2025.
**Source:** [arXiv](https://arxiv.org/)

| Aspect | Details |
|--------|---------|
| **Product** | Google's NotebookLM |
| **Approach** | Users upload source documents; LLM answers ONLY from those sources (grounded generation) |
| **Key innovation** | Source-grounded RAG — eliminates hallucination by restricting answers to uploaded materials |
| **Features** | Audio overviews (podcast-style summaries), source citations, collaborative notebooks |
| **Implication for VzdelAI** | Model for source-grounded responses with explicit citations; validates RAG approach for educational accuracy |

---

## 2. Effectiveness Evidence

### 2.1 AI Personalization at Scale (Dartmouth, 2025)

**Source:** Dartmouth College research study, 2025.

- **Finding:** AI can deliver **personalized learning at scale** that was previously only possible with 1:1 human tutoring
- **Context:** Introductory STEM courses with hundreds of students
- **Mechanism:** AI adapts difficulty, pacing, and explanation style based on student responses
- **Limitation:** Effectiveness depends on quality of knowledge base and prompt design
- **Relevance:** Validates VzdelAI's core premise — AI can bridge the personalization gap in large university courses

### 2.2 Teacher Time Savings

Multiple studies consistently report significant time savings:

| Study | Finding | Source |
|-------|---------|--------|
| Gallup/Walton Family Foundation (2025) | Teachers using AI weekly save **~5.9 hours/week** | [Gallup](https://news.gallup.com/poll/691967/three-teachers-weekly-saving-six-weeks-year.aspx) |
| Gradescope data | **30–50% grading time reduction** with AI-assisted grading | [Gradescope](https://www.gradescope.com/) |
| Century Tech | Teachers report **significant time savings** on differentiation | [Century Tech](https://www.century.tech/) |
| UNESCO (2025) | AI has "potential to reduce administrative burden" | [UNESCO](https://www.unesco.org/) |

### 2.3 RAG vs. LLM-Only Performance

| Study | LLM-Only Accuracy | RAG-Enhanced Accuracy | Improvement |
|-------|-------------------|----------------------|-------------|
| LPITutor (2025) | 72% | **94%** | +30.5% |
| Jill Watson vs. ChatGPT | ChatGPT lower | Jill Watson higher | Domain-specific wins |
| NotebookLM | N/A (source-grounded) | High (by design) | Eliminates hallucination |

**Conclusion:** RAG is not optional — it is essential for educational AI accuracy.

### 2.4 Student Adoption & Perception

| Metric | Value | Source |
|--------|-------|--------|
| UK undergraduate students using AI tools | **92%** (2025) | HEPI/Kortext |
| Year-over-year increase | From 66% to 92% | HEPI/Kortext |
| Students who find AI helpful for learning | ~75% | Various surveys |
| Students worried about over-reliance | **59%** | EDUCAUSE |
| Students wanting institutional AI policies | ~80% | Multiple studies |

---

## 3. Pedagogical Frameworks

### 3.1 UNESCO: "AI and the Future of Education" (2025)

**Citation:** UNESCO. (2025). *AI and the Future of Education: Disruptions, Dilemmas and Directions.*
**Source:** [UNESCO](https://www.unesco.org/en/digital-education/artificial-intelligence)

Key positions:
- AI should **augment, not replace** teachers
- Emphasis on **human oversight** of AI in educational decisions
- Call for **AI literacy** as a core competency for both teachers and students
- Warning against algorithmic determinism in student assessment
- Recommendation for **ethical frameworks** before deployment

### 3.2 OECD-EC: AI Literacy Framework

**Citation:** OECD & European Commission. (2025–2026). *AI Literacy Framework for Primary and Secondary Education.*
**Source:** [OECD AI Policy Observatory](https://oecd.ai/)

| Phase | Status | Content |
|-------|--------|---------|
| Draft framework | Published 2025 | Core AI literacy competencies for K-12 |
| Final framework | Expected 2026 | Complete with assessment rubrics and implementation guides |

Key competencies defined:
1. Understanding AI concepts and capabilities
2. Critically evaluating AI outputs
3. Using AI tools effectively and ethically
4. Understanding AI's societal impact
5. Data literacy and privacy awareness

**Relevance:** VzdelAI should embed AI literacy scaffolding — helping students understand how the AI works, its limitations, and how to evaluate its responses.

### 3.3 Bloom's Taxonomy with AI Augmentation

Traditional Bloom's taxonomy can be mapped to AI capabilities:

| Bloom's Level | Traditional Activity | AI-Augmented Activity |
|---------------|---------------------|----------------------|
| **Remember** | Recall facts | AI provides instant factual retrieval (RAG) |
| **Understand** | Explain concepts | AI explains in multiple ways, adapts to student level |
| **Apply** | Solve problems | AI generates practice problems, provides scaffolded hints |
| **Analyze** | Compare, contrast | AI helps structure analysis, provides additional perspectives |
| **Evaluate** | Judge, critique | AI presents arguments/counter-arguments for student evaluation |
| **Create** | Design, produce | AI assists in drafting, student refines and creates |

**Key principle for VzdelAI:** AI should primarily support **lower Bloom's levels** (Remember, Understand) autonomously, while scaffolding higher levels (Apply, Analyze, Evaluate, Create) through **Socratic questioning** — never doing the higher-order thinking for the student.

### 3.4 OECD: "What Should Teachers Teach in a Future of Powerful AI?"

**Citation:** OECD. (2025). *What should teachers teach and students learn in a future of powerful AI?*
**Source:** [OECD Education](https://www.oecd.org/en/topics/education.html)

Key recommendations:
- Shift from **knowledge transmission** to **knowledge application and critical thinking**
- Teachers should focus on what AI cannot do: mentoring, motivation, social skills, ethical reasoning
- Assessment must evolve — traditional exams are increasingly vulnerable to AI assistance
- AI fluency should be embedded across subjects, not taught in isolation
- Collaborative human-AI workflows should be the norm, not the exception

---

## 4. Central & Eastern European AI Education Projects

### 4.1 Slovakia: National AI Education Plan 2025–2027

**Source:** Ministerstvo školstva, výskumu, vývoja a mládeže SR (MŠVVaM SR). (2025). *Plán zodpovedného využívania AI vo vzdelávaní 2025–2027.*
**URL:** [MŠVVaM SR](https://www.minedu.sk/)

| Aspect | Details |
|--------|---------|
| **Title** | Plán zodpovedného využívania AI vo vzdelávaní (Responsible Use of AI in Education Plan) |
| **Period** | 2025–2027 |
| **Key measures** | AI in curricula from 2026/2027; teacher training; AI Competence Centres |
| **AI Competence Centres** | At selected Slovak universities (2026–2029) |
| **Funding** | State budget + EU structural funds |
| **BratislavAI Forum** | Regular ministerial meetings on AI policy in education |

**Relevance to VzdelAI:** Direct alignment — VzdelAI at University of Žilina could serve as a pilot project supporting the national plan's objectives. Potential for funding through national AI education initiatives.

### 4.2 Slovakia: AI Competence Centres at Universities (2026–2029)

| Aspect | Details |
|--------|---------|
| **Purpose** | Build AI expertise and infrastructure at Slovak universities |
| **Timeline** | 2026–2029 |
| **Activities** | Research, development, training, knowledge transfer |
| **Funding** | EU funds + national co-financing |
| **Opportunity** | University of Žilina could host or participate in a Centre, with VzdelAI as a flagship project |

### 4.3 AI-EmpaTe Project (2024–2026)

**Source:** Erasmus+ funded project
**Partners:** Czechia, Latvia, Slovak Republic

| Aspect | Details |
|--------|---------|
| **Full name** | AI-Empowered Teachers (AI-EmpaTe) |
| **Funding** | Erasmus+ |
| **Period** | 2024–2026 |
| **Goal** | Develop teacher competencies for AI integration in education |
| **Partners** | Institutions from Czechia, Latvia, Slovakia |
| **Outputs** | Training materials, best practice guides, teacher workshops |
| **Relevance** | Potential collaboration and knowledge sharing for VzdelAI teacher tools |

### 4.4 Poland: AI4Youth & "Lesson: AI"

| Programme | Period | Description |
|-----------|--------|-------------|
| **AI4Youth** | 2020–2025 | Student-focused AI education programme (EU-funded) |
| **"Lesson: AI"** (Lekcja: AI) | 2025–2027 | Teacher training programme for AI in the classroom |

**Source:** Polish Ministry of Education; European Commission AI education funding

### 4.5 Erasmus+ Forward-Looking Projects: Topic 7

| Aspect | Details |
|--------|---------|
| **Call** | Erasmus+ Forward-Looking Projects |
| **Topic 7** | Ethical and effective use of AI in education |
| **Funding** | Up to €1.5M per project |
| **Focus** | Developing ethical frameworks, teacher training, piloting AI tools |
| **Relevance** | VzdelAI could pursue Erasmus+ funding for scaling beyond University of Žilina |

---

## 5. Research Gaps & Opportunities

### Identified Gaps

| Gap | Description | VzdelAI Opportunity |
|-----|-------------|---------------------|
| **Non-English AI tutoring** | Most research on English-language platforms | Slovak + multilingual AI tutoring research |
| **Higher Ed focus** | Many systems target K-12 | University-level AI tutoring evaluation |
| **EU regulatory compliance** | Limited research on AI Act-compliant educational AI | First-mover advantage in EU-compliant platform |
| **CEE context** | Minimal research from Central/Eastern European universities | Publish findings in CEE educational context |
| **Long-term impact** | Most studies are short-term (1 semester) | Longitudinal study across multiple semesters |
| **Teacher tool evaluation** | Most research focuses on student-facing AI | Evaluate impact of AI tools on teacher effectiveness |

### Publication Opportunities

| Venue | Type | Relevance |
|-------|------|-----------|
| *Computers & Education* | Journal | Top-tier journal for educational technology |
| *British Journal of Educational Technology* | Journal | AI in education special issues |
| *International Journal of AI in Education* | Journal | Specialized in AI + education intersection |
| *LAK (Learning Analytics & Knowledge)* | Conference | Learning analytics from VzdelAI data |
| *AIED (AI in Education)* | Conference | Annual conference on AI in education |
| *ECTEL (European Conference on TEL)* | Conference | European focus, relevant for EU context |
| *PeerJ Computer Science* | Journal | Open access, rapid publication (LPITutor published here) |

---

## References

- Alnawas, A., & Al-Araji, Z. (2025). LPITutor: AI-powered intelligent tutoring system using RAG and prompt engineering. *PeerJ Computer Science*, 11, e2289. https://doi.org/10.7717/peerj-cs.2289
- Goel, A., & Polepeddi, L. (2018). Jill Watson: A Virtual Teaching Assistant for Online Education. Georgia Institute of Technology. https://dilab.gatech.edu/jill-watson/
- UNESCO. (2025). *AI and the Future of Education: Disruptions, Dilemmas and Directions.* https://www.unesco.org/en/digital-education/artificial-intelligence
- OECD. (2025). *What should teachers teach and students learn in a future of powerful AI?* https://www.oecd.org/en/topics/education.html
- OECD & European Commission. (2025). *AI Literacy Framework for Primary and Secondary Education.* https://oecd.ai/
- HEPI/Kortext. (2025). *Student Generative AI Survey 2025.* https://www.hepi.ac.uk/reports/student-generative-ai-survey-2025/
- EDUCAUSE. (2025). *2025 EDUCAUSE AI Landscape Study.* https://library.educause.edu/resources/2025/2/2025-educause-ai-landscape-study
- Gallup/Walton Family Foundation. (2025). *Teaching for Tomorrow: Unlocking Six Weeks a Year With AI.* https://news.gallup.com/poll/691967/three-teachers-weekly-saving-six-weeks-year.aspx
- MŠVVaM SR. (2025). *Plán zodpovedného využívania AI vo vzdelávaní 2025–2027.* https://www.minedu.sk/
- European Commission. (2025). *Erasmus+ Programme Guide — Forward-Looking Projects.* https://erasmus-plus.ec.europa.eu/
