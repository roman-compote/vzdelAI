# 02 — Platform Landscape: AI Education Platforms Analysis

> Comprehensive analysis of existing AI education platforms, categorized by approach, audience, and capabilities.

---

## 1. LLM-Based AI Tutors

### Overview Table

| Platform | LLM Technology | Target Audience | Pricing | Key Feature |
|----------|---------------|-----------------|---------|-------------|
| **Khanmigo** | GPT-4 + Phi-3 | K-12, Higher Ed | Free (teachers), $4/mo (learners) | Socratic questioning, Khan Academy content integration |
| **ChatGPT Edu** | GPT-5 | Higher Education | Custom per university | Campus-wide deployment, custom GPTs, enterprise security |
| **Microsoft Copilot for Education** | GPT-4 | K-12, Higher Ed | $18/user/month | Integrated into M365 (Word, PPT, Teams, OneNote) |
| **Coursera Coach** | GPT-4 | HE, Corporate | Subscription-based | In-course Q&A, video summarization, exercise feedback |
| **Duolingo Max** | GPT-4 | Language learners | Premium tier | Roleplay conversations, Explain My Answer |
| **Google Gemini** | Gemini | K-12, Higher Ed | Various tiers | Research-aware, search integration, multimodal |

### Detailed Platform Profiles

#### Khanmigo (Khan Academy)

- **Technology:** GPT-4 for complex reasoning, Phi-3 (Microsoft) for lighter tasks
- **Approach:** Socratic method — asks guiding questions rather than giving direct answers
- **Teacher features:** Lesson planning, rubric creation, student progress insights
- **Student features:** Tutoring across math/science/humanities, writing coach, coding help
- **Integration:** Standalone platform; Khan Academy content library as knowledge base
- **Notable:** Pioneered the "AI tutor that doesn't give answers" paradigm; heavily influenced by learning science research on productive struggle
- **Pricing shift (2025):** Made free for teachers, $4/month for individual learners — signaling market accessibility trend
- **Source:** [Khan Academy — Khanmigo](https://www.khanacademy.org/khan-labs)

#### ChatGPT Edu (OpenAI)

- **Technology:** GPT-5 (latest model), with custom GPT creation capabilities
- **Approach:** General-purpose LLM with institution-level customization
- **Key features:**
  - Campus-wide deployment with institutional controls
  - Custom GPTs for specific courses/departments
  - Enterprise-grade security (SOC 2, data not used for training)
  - Group workspaces for collaborative AI use
  - Web browsing, data analysis, and code interpretation
- **Deployment:** University IT manages access; per-institution licensing
- **Notable:** Over 15 universities launched with ChatGPT Edu by 2025, including ASU, Wharton, Oxford
- **Source:** [OpenAI — ChatGPT Edu](https://openai.com/chatgpt/education/)

#### Microsoft Copilot for Education

- **Technology:** GPT-4 via Azure OpenAI, deeply integrated into Microsoft 365
- **Approach:** AI embedded within existing productivity tools teachers already use
- **Key features:**
  - AI in Word (lesson plan generation), PowerPoint (presentation creation)
  - AI in Teams (meeting summaries, Q&A bots)
  - AI in OneNote (content organization, student support)
  - Reading Coach with AI-powered fluency practice
  - "Teach" module for unified lesson planning workflow (2025)
  - "Study and Learn" student agent (preview Jan 2026)
- **Pricing:** $18/user/month (from Dec 2025)
- **Notable:** Strongest integration play — no new platform to adopt; leverages existing M365 ecosystem
- **Source:** [Microsoft Education Blog](https://educationblog.microsoft.com/)

→ *Detailed MS Teams analysis:* [04-ms-teams-integration.md](04-ms-teams-integration.md)

#### Coursera Coach

- **Technology:** GPT-4, integrated within Coursera course experience
- **Features:** In-video Q&A, content summarization, quiz preparation, exercise feedback
- **Target:** Higher education and corporate training enrolled in Coursera courses
- **Approach:** Context-aware — understands the specific course content being studied
- **Source:** [Coursera — AI in Learning](https://www.coursera.org/)

#### Duolingo Max

- **Technology:** GPT-4 for conversation features
- **Key features:**
  - "Roleplay" — simulated real-world conversations in target language
  - "Explain My Answer" — detailed grammar/vocabulary explanations
- **Approach:** Gamification + AI for immersive language practice
- **Notable:** Demonstrates effective AI integration within an existing learning product
- **Source:** [Duolingo Blog — Duolingo Max](https://blog.duolingo.com/)

#### Google Gemini for Education

- **Technology:** Gemini family of models (multimodal)
- **Key features:**
  - Research-aware with integrated Google Search
  - Multimodal: text, image, audio, video understanding
  - Google Workspace for Education integration
  - NotebookLM for source-grounded AI assistance
- **Notable:** NotebookLM uses RAG by design — users upload sources, AI answers only from those sources
- **Source:** [Google for Education](https://edu.google.com/)

---

## 2. Adaptive Learning Platforms

### Overview Table

| Platform | Approach | Target Audience | Notable Feature |
|----------|----------|-----------------|-----------------|
| **Squirrel AI** | Granular knowledge-point system | K-12 (China) | Pioneer in adaptive learning, rural deployment |
| **Century Tech** | Cognitive neuroscience + AI | K-12 (UK) | Real-time student dashboards, micro-lessons |
| **Carnegie Learning MATHia** | Cognitive tutoring model | K-12 Mathematics | Research-backed, step-level adaptivity |
| **ALEKS** (McGraw-Hill) | Knowledge space theory | K-12, Higher Ed | Adaptive assessment, individualized learning paths |
| **Knewton** (Wiley) | Adaptive courseware | Higher Education | Content-agnostic personalization engine |

### Detailed Platform Profiles

#### Squirrel AI (Yixue Group)

- **Origin:** China, one of the earliest large-scale adaptive learning deployments
- **Approach:** Decomposes subjects into ultra-granular "knowledge points" (10x finer than typical curricula)
- **Technology:** Bayesian knowledge tracing, multi-armed bandit algorithms for content selection
- **Scale:** Millions of students across China, including rural/underserved areas
- **Key finding:** In controlled studies, Squirrel AI students outperformed those with human-only instruction
- **Relevance to VzdelAI:** Demonstrates that fine-grained knowledge modeling improves personalization
- **Source:** [Squirrel AI](https://squirrelai.com/)

#### Century Tech

- **Origin:** UK-based platform combining cognitive neuroscience, data science, and AI
- **Approach:** Creates "micro-lessons" adapting in real-time to student performance
- **Teacher dashboard:** Real-time visibility into class and individual student knowledge states
- **Assessment:** Continuous, embedded assessment (no separate test events)
- **Key finding:** Teachers report significant time savings on differentiation
- **Relevance to VzdelAI:** Model for real-time teacher dashboards and adaptive content delivery
- **Source:** [Century Tech](https://www.century.tech/)

#### Carnegie Learning MATHia

- **Approach:** Based on ACT-R cognitive tutoring theory from Carnegie Mellon
- **Adaptivity:** Step-level — adapts not just which problem to show but provides hints at each solution step
- **Research:** Extensive longitudinal studies showing improved math outcomes
- **Relevance to VzdelAI:** Gold standard for research-backed adaptive tutoring; model for step-level scaffolding
- **Source:** [Carnegie Learning](https://www.carnegielearning.com/)

#### ALEKS (McGraw-Hill)

- **Technology:** Knowledge Space Theory — maps prerequisite relationships between concepts
- **Approach:** Periodically reassesses what students know and adjusts learning path
- **Subjects:** Math, chemistry, statistics, business, and more
- **Scale:** Widely adopted in US higher education
- **Relevance to VzdelAI:** Demonstrates knowledge-space-based adaptivity for university-level courses
- **Source:** [ALEKS](https://www.aleks.com/)

#### Knewton (now Wiley)

- **Approach:** Content-agnostic adaptive engine — works with publisher content
- **Technology:** Probabilistic graphical models for learner proficiency estimation
- **Integration:** Embedded within Wiley courseware products
- **Relevance to VzdelAI:** Shows how an adaptive engine can be separated from content layer
- **Source:** [Wiley — Knewton](https://www.wiley.com/)

---

## 3. Assessment & Feedback Platforms

| Platform | Core Feature | Impact | Target |
|----------|-------------|--------|--------|
| **Gradescope** (Turnitin) | AI-assisted grading, answer grouping, rubric application | 30–50% grading time reduction | Higher Education |
| **Turnitin** | AI writing detection, originality checking | Academic integrity enforcement | K-12, Higher Ed |

### Gradescope

- **Approach:** AI groups similar student answers, allowing batch grading with consistent rubric application
- **Features:** Handwriting recognition, code autograding, flexible rubric management
- **Impact:** Instructors report 30–50% reduction in grading time; improved consistency
- **AI detection:** Now includes AI-writing detection capabilities alongside originality checks
- **Source:** [Gradescope](https://www.gradescope.com/)

### Turnitin

- **AI detection:** Launched AI writing detection tool (2023–2025) identifying LLM-generated text
- **Accuracy claims:** 98% accuracy for full AI-generated text; lower for mixed human/AI content
- **Controversy:** False positive concerns, particularly for non-native English speakers
- **Relevance to VzdelAI:** Academic integrity tooling must be considered alongside AI tutoring
- **Source:** [Turnitin](https://www.turnitin.com/)

---

## 4. University-Developed Systems

### Jill Watson (Georgia Tech)

- **Origin:** Created by Prof. Ashok Goel at Georgia Tech for the OMSCS program (600+ students)
- **Purpose:** AI teaching assistant for answering routine course questions on discussion forums
- **Performance:**
  - 75–97% accuracy on test question sets
  - **Outperforms ChatGPT** in classroom settings due to course-specific training
  - Students initially unaware they were interacting with AI
- **Impact:**
  - Enhanced **teaching presence** — students felt more supported
  - Enhanced **social presence** — more engagement on forums
  - Human TAs freed to handle complex questions
- **Architecture:** Knowledge-based system with course-specific document corpus
- **Key insight:** Domain-specific, RAG-enhanced systems outperform general-purpose LLMs in educational contexts
- **Source:** Goel, A., & Polepeddi, L. (2018). *Jill Watson: A Virtual Teaching Assistant for Online Education.* Georgia Tech. ([Research paper](https://dilab.gatech.edu/jill-watson/))

---

## 5. Comparative Analysis for VzdelAI

### Feature Comparison Matrix

| Feature | Khanmigo | ChatGPT Edu | Copilot Edu | Squirrel AI | Jill Watson |
|---------|----------|-------------|-------------|-------------|-------------|
| Socratic method | ✅ | ❌ | ❌ | ❌ | ❌ |
| RAG/domain-specific | ✅ | Partial | Partial | ✅ | ✅ |
| Adaptive learning | Limited | ❌ | ❌ | ✅ | ❌ |
| Teacher tools | ✅ | ✅ | ✅ | ✅ | ❌ |
| LMS integration | ❌ | Limited | ✅ (M365) | ✅ | ❌ |
| Open-source | ❌ | ❌ | ❌ | ❌ | ❌ |
| On-premise option | ❌ | ❌ | ❌ | ❌ | ✅ |
| EU data compliance | Unknown | SOC 2 | ✅ | ❌ | ✅ |
| Multi-language | Limited | ✅ | ✅ | Chinese only | English only |

### Key Takeaways for VzdelAI

1. **No single platform covers all needs** — VzdelAI should combine best elements from multiple categories
2. **Khanmigo's Socratic approach** is the gold standard for AI tutoring pedagogy
3. **Copilot for Education** is the strongest ecosystem play for MS Teams-based institutions
4. **Jill Watson** proves that domain-specific RAG outperforms general LLMs in education
5. **Adaptive platforms** (Squirrel AI, Century Tech) show the value of fine-grained knowledge modeling
6. **No major platform is open-source** — opportunity for VzdelAI to leverage open-source patterns where appropriate within the Microsoft-native stack
7. **EU compliance** is not a primary feature of US/China platforms — VzdelAI must address this independently

---

## References

- Khan Academy. (2025). *Khanmigo AI Tutor*. https://www.khanacademy.org/khan-labs
- OpenAI. (2025). *ChatGPT Edu*. https://openai.com/chatgpt/education/
- Microsoft. (2025). *Copilot for Education*. https://educationblog.microsoft.com/
- Coursera. (2025). *AI-Powered Learning*. https://www.coursera.org/
- Duolingo. (2025). *Duolingo Max Features*. https://blog.duolingo.com/
- Google. (2025). *Google for Education — AI Tools*. https://edu.google.com/
- Squirrel AI. (2025). *Adaptive Learning Platform*. https://squirrelai.com/
- Century Tech. (2025). *AI-Powered Teaching and Learning*. https://www.century.tech/
- Carnegie Learning. (2025). *MATHia Adaptive Platform*. https://www.carnegielearning.com/
- McGraw-Hill. (2025). *ALEKS Adaptive Learning*. https://www.aleks.com/
- Gradescope. (2025). *AI-Assisted Grading*. https://www.gradescope.com/
- Turnitin. (2025). *AI Writing Detection*. https://www.turnitin.com/
- Goel, A., & Polepeddi, L. (2018). *Jill Watson: A Virtual Teaching Assistant for Online Education*. Georgia Institute of Technology. https://dilab.gatech.edu/jill-watson/
