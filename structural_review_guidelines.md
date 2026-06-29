# Structural Review Guidelines

## Purpose & Scope
These guidelines direct the **Structural Review Agent** to evaluate overall course organization, taxonomy, learning objectives, learner onboarding, competitive positioning, and long-term maintenance strategy.

---

## Review Workflow
1. **Pre‑review checklist** – ensure repository builds, CI passes, and documentation is present.
2. **Structural analysis** – evaluate course outline, dual‑track clarity, module naming, model references, and learner experience flow.
3. **Competitive scan** – verify the course offers differentiated value vs. top competing courses.
4. **Maintenance audit** – confirm a post-publication review cycle is defined.
5. **Generate report** – produce a structured output using the schema defined below.

---

## Evaluation Criteria (5‑point scale)

| Criterion | Description |
|-----------|-------------|
| **Accuracy** | Facts and model references are current (2026). |
| **Learning Objectives** | Clear, measurable outcomes per lesson. |
| **Course Taxonomy** | Proper classification of technical topics. |
| **Instructional Design** | Logical flow, pacing, and dual‑track clarity. |
| **Learner Experience** | Smooth onboarding, appropriate cognitive load, and gradual difficulty ramp. |
| **Assessment Design** | Capstone and exercises include self-evaluation rubrics with measurable success criteria. |
| **Competitive Differentiation** | Course covers topics not found in the top 5 competing courses. |
| **Maintenance Readiness** | A defined review cycle and "last verified" dates on volatile references. |
| **Versioning** | Consistent `MAJOR.MINOR` versioning. |

---

## Scoring Rubric
- **5 – Excellent**: No changes needed; course structure is production-ready.
- **4 – Good**: Minor tweaks optional.
- **3 – Satisfactory**: Several actionable suggestions required.
- **2 – Poor**: Significant structural issues; must be fixed before publishing.
- **1 – Unacceptable**: Fundamental flaws; reject.

---

## Structural Review Checklist

### Core Structure
```markdown
- [ ] Course outline matches stated learning objectives.
- [ ] Dual‑track (conceptual vs. technical) is clearly delineated.
- [ ] All modules have consistent naming and versioning.
- [ ] Up‑to‑date references to LLM models and APIs.
- [ ] Taxonomy categories are accurate and complete.
- [ ] Root metadata.json includes a valid "curriculum" manifest mapping all modules and lessons.
- [ ] Companion files (.md and .ipynb) for the same lesson are properly paired in the "modes" schema of metadata.json rather than listed as duplicate standalone lessons.
- [ ] Python notebook lessons include a valid "Open in Colab" launch badge link at the top of the lesson file for zero-friction browser execution.
```

### Learner Experience & Onboarding
```markdown
- [ ] Prerequisites are explicitly listed at the course and module level.
- [ ] A "Who This Course Is For" section sets accurate audience expectations.
- [ ] Each lesson can be completed in ≤ 30 minutes (including exercises).
- [ ] Difficulty progression is gradual — no sudden jumps in assumed knowledge.
- [ ] The first lesson is completable by someone with zero prior context in the topic.
- [ ] Drop-off risk points (e.g., first coding exercise, environment setup) are identified and mitigated.
```

### Assessment & Capstone Design
```markdown
- [ ] Capstone/final project includes a self-assessment rubric with measurable success criteria (e.g., cost, latency, output accuracy).
- [ ] Each module has at least one exercise with a verifiable expected output.
- [ ] Grading criteria are transparent — students know what "good" looks like before they start.
```

### Competitive Differentiation
```markdown
- [ ] Course covers at least 2 topics not found in the top 5 competing courses on the same subject.
- [ ] Unique pedagogical features (e.g., dual-track system, role-specific tabs) are explicitly highlighted.
- [ ] Real-world case studies are used instead of toy/generic examples.
```

### Post-Publication Maintenance
```markdown
- [ ] A quarterly review schedule is defined (AI/ML content rots within 3–6 months).
- [ ] Model name and API version references include a "last verified" date.
- [ ] Student feedback from the first cohort is incorporated within 30 days of launch.
- [ ] Drop-off analytics are reviewed to identify and fix problematic lessons.
- [ ] A CHANGELOG.md tracks all structural changes post-publication.
```

---

## Agent Output Schema

The Structural Review Agent should produce a report with the following sections (modeled on the format of [course_review.md](file:///C:/vinod/course-repo/Prompt-Engineering-Mastery/Prompt-Engineering-Mastery/reports/course_review.md)):

```markdown
# Structural Review Report: <Course Name>

## 1. Course Organization & Taxonomy
- Summary of module structure, naming consistency, and dual-track clarity.
- Table of any misaligned learning objectives.

## 2. Learner Experience Assessment
- Prerequisites analysis.
- Lesson-by-lesson time estimate and cognitive load assessment.
- Identified drop-off risk points with mitigation recommendations.

## 3. Model & API Reference Audit
| Reference | File(s) | Status | Recommendation |
|-----------|---------|--------|----------------|
| ...       | ...     | ...    | ...            |

## 4. Assessment & Capstone Review
- Capstone rubric evaluation.
- Module-level exercise verification.

## 5. Competitive Positioning
- Differentiated topics identified.
- Comparison with top competing courses.

## 6. Maintenance Readiness
- Review cycle status.
- Volatile references flagged.

## 7. Overall Score & Verdict
| Criterion               | Score (1–5) |
|--------------------------|-------------|
| Accuracy                 |             |
| Learning Objectives      |             |
| Learner Experience       |             |
| Assessment Design        |             |
| Competitive Differentiation |          |
| Maintenance Readiness    |             |
| **Overall**              |             |

**Verdict:** <Approve / Revise / Reject>
```

---
*Generated by Antigravity AI assistant.*
