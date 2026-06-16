# Pedagogical & Technical Critique Guidelines

## Purpose & Scope
These guidelines direct the **Pedagogical & Technical Critique Agent** to evaluate teaching effectiveness, instructional design, code quality, environment setup, AI-generation indicators, security practices, and production-readiness of the course.

---

## Review Workflow
1. **Environment audit** – verify that setup instructions, dependencies, and API key management are complete and cross-platform.
2. **Pedagogical analysis** – evaluate the dual‑track system, interactive pacing, active recall, and cognitive load.
3. **Code & SDK analysis** – verify correctness, modern library usage, error handling, and production patterns.
4. **AI-generation scan** – systematically check for hallucinated model names, fabricated specs, and templated AI phrasing.
5. **Security & robustness review** – assess guardrail implementation, input/output sanitization, and safety classifier usage.
6. **Generate report** – produce a structured output using the schema defined below.

---

## Evaluation Criteria (5‑point scale)

| Criterion | Description |
|-----------|-------------|
| **Pedagogical Design** | Clear separation of Core Concepts vs. Technical Deep-Dives; effective pacing and cognitive load management. |
| **Active Engagement** | Varied formatting of concept checks, quizzes, role-specific tabs (e.g., PM, Marketer, Developer). |
| **Environment & Setup** | Complete, cross-platform setup guide with pinned dependencies and secure API key management. |
| **Code Quality & SDKs** | Code correctness, PEP-8 compliance, up-to-date SDK APIs (OpenAI, Anthropic, Google GenAI). |
| **AI-Generation Cleanliness** | No hallucinated model names, fabricated specs, or templated AI transition phrases. |
| **Tech Depth & Relevance** | Coverage of critical production concepts: prompt caching, RAG integration, routing, latency/cost optimization. |
| **Security & Robustness** | Real-world safety guardrails, error handling in pipelines, input/output sanitization. |

---

## Scoring Rubric
- **5 – Excellent**: Exceptionally engaging, technically robust, production-grade code, human-authored tone throughout.
- **4 – Good**: Highly effective with minor pedagogical or technical improvements recommended.
- **3 – Satisfactory**: Good foundation but lacks depth in advanced topics (caching, security) or has repetitive pacing.
- **2 – Poor**: Non-runnable code, heavily templated/AI-like language, or weak security/error handling.
- **1 – Unacceptable**: Broken code, misleading instruction, or major pedagogical deficiencies.

---

## Checklists

### Environment & Setup Audit
```markdown
- [ ] A dedicated setup guide covers Python version, virtual environment creation, and dependency installation.
- [ ] A `requirements.txt` or `pyproject.toml` with pinned dependency versions is provided.
- [ ] API key management uses `.env` files with explicit warnings against hardcoding secrets.
- [ ] Setup instructions have been tested on at least 2 OS environments (e.g., Windows + macOS/Linux).
- [ ] A Docker or devcontainer option is available for zero-friction setup.
- [ ] The first code sample runs successfully after following only the setup guide.
```

### Pedagogical Design
```markdown
- [ ] Concept checks are varied — not every lesson uses identical `<details><summary>` disclosure patterns.
- [ ] Some concept checks are open-ended reflection prompts; others are inline quizzes or multiple-choice.
- [ ] Role-specific tabs (PM, Marketer, Developer, Analyst) are used where appropriate.
- [ ] Each lesson has a clear roadmap table showing who should read which section.
- [ ] Cognitive load per lesson is appropriate (≤ 20 minutes of new concepts before a practice exercise).
```

### AI-Generation Detection (Specific)
```markdown
- [ ] Every model name referenced in the course is cross-checked against official release pages.
- [ ] No hallucinated model names or version numbers (e.g., "GPT-4.1", "Claude Sonnet 4", "o4-mini", "Llama 4 Scout").
- [ ] No fabricated context window sizes, pricing figures, or release dates.
- [ ] No fabricated API model string identifiers (e.g., "claude-sonnet-4-20250514").
- [ ] Transition phrases are direct and human — flag and rewrite phrases like:
      "Here's a hard truth", "Before you can command...", "The fix is deceptively simple",
      "Let's dive deep", "In today's rapidly evolving landscape".
- [ ] Concept Check formatting varies across lessons — not a uniform template.
- [ ] Lists and section structures are not suspiciously uniform across all lesson files.
```

### Code Quality & SDK Correctness
```markdown
- [ ] Code samples use correct instantiation and parameter structures for modern SDKs.
- [ ] OpenAI SDK: correct client instantiation, messages array, Pydantic-enforced structured outputs.
- [ ] Anthropic SDK: system instructions separated as top-level parameter; XML tags used for Claude.
- [ ] Google GenAI SDK: uses `from google import genai` (not legacy `google-generativeai`).
- [ ] Multi-API pipelines demonstrate proper error boundaries (e.g., `asyncio.gather` with `return_exceptions=True` or try-except).
- [ ] All code follows PEP-8 conventions.
```

### Production Best Practices
```markdown
- [ ] Prompt caching is taught — Anthropic/Google prefix matching, API syntax, cost/latency impact.
- [ ] RAG-specific prompting is covered — document citation format, source conflict handling, grounding instructions.
- [ ] Model routing is demonstrated — using cheap models for simple tasks, premium models for complex ones.
- [ ] Evaluation practices include empirical metrics (not just subjective assessment).
```

### Security & Robustness
```markdown
- [ ] System instructions are explicitly described as a *soft* boundary, not a security guarantee.
- [ ] Dedicated safety classifiers (e.g., Llama Guard) are taught alongside instruction-based guardrails.
- [ ] Both input AND output sanitization are covered.
- [ ] String-matching sanitization is labeled as a baseline educational model with warnings about production fragility.
- [ ] Common attack vectors are discussed: jailbreaks, indirect prompt injection, cipher-based injection.
```

---

## Agent Output Schema

The Pedagogical & Technical Critique Agent should produce a report with the following sections (modeled on [course_critique.md](file:///C:/vinod/course-repo/Prompt-Engineering-Mastery/Prompt-Engineering-Mastery/reports/course_critique.md)):

```markdown
# Pedagogical & Technical Critique Report: <Course Name>

## 1. Environment & Setup Assessment
- Setup guide completeness.
- Dependency management quality.
- Cross-platform test results.

## 2. Pedagogical Design & Readability
### 2.1 Dual-Track Evaluation
- Effectiveness of Core Concept vs. Technical Deep-Dive separation.

### 2.2 Interactive Pacing & Engagement
- Concept check variety.
- Cognitive load per lesson.
- Role-specific content effectiveness.

## 3. AI-Generation Cleanliness
| Indicator Type | File(s) | Finding | Recommendation |
|----------------|---------|---------|----------------|
| Hallucinated model name | ... | ... | ... |
| Templated phrasing | ... | ... | ... |
| Uniform formatting | ... | ... | ... |

## 4. Technical Code & API Analysis
### 4.1 SDK Integration Quality
- Per-provider assessment (OpenAI, Anthropic, Google GenAI).

### 4.2 Areas for Technical Refinement
- Specific code issues with file locations and fixes.

## 5. Production Readiness
- Prompt caching coverage.
- RAG integration coverage.
- Model routing and cost optimization.

## 6. Security & Robustness
- Guardrail implementation assessment.
- Sanitization and attack vector coverage.

## 7. Overall Rating & Assessment
| Criterion                  | Score (1–5) |
|----------------------------|-------------|
| Pedagogical Design         |             |
| Active Engagement          |             |
| Environment & Setup        |             |
| Code Quality & SDKs        |             |
| AI-Generation Cleanliness  |             |
| Tech Depth & Relevance     |             |
| Security & Robustness      |             |
| **Overall**                |             |

**Verdict:** <Summary assessment with key recommendations>
```

---
*Generated by Antigravity AI assistant.*
