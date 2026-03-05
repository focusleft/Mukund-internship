# Mukund Internship — Robotics Resume Pipeline

Resume optimization pipeline targeting **Software Robotics internships** (Summer 2026). Built by scanning 30+ real job postings and reverse-engineering the resume to match what recruiters and ATS systems actually screen for.

---

## Quick Links

### Final Deliverables
- [Final Resume](04-output/final-resume.md) — the rewritten, ATS-optimized resume
- [ATS Checklist & LinkedIn](04-output/ats-checklist-and-linkedin.md) — keyword coverage, LinkedIn headline, LinkedIn About, top 5 roles to apply
- [Why This Resume Works](04-output/why-this-resume-works.md) — section-by-section breakdown of design decisions

### Research
- [Job Market Scan Results](03-research/job-market-scan-results.md) — 30+ postings, application guide, skills gap analysis, fine-tuning recommendations

### Prompts (reusable)
- [Resume Rewrite Prompt](02-prompts/resume-rewrite-prompt.md) — master prompt with market intelligence, keyword tiers, project rename mappings, bullet examples
- [Job Market Scan Prompt](02-prompts/job-market-scan-prompt.md) — prompt for refreshing job postings and skills gap data

### Original Materials
- [Original Resume (PDF)](01-original/original-resume.pdf)
- [Original Resume (text)](01-original/original-resume.md)

### Instructions
- [How to Regenerate & Finalize](how-to-regenerate.md) — workflow, regeneration steps, submission checklist

---

## Directory Structure

```
mukund-internship/
|
|-- 01-original/
|   |-- original-resume.pdf           # Starting PDF
|   |-- original-resume.md            # Plain-text input for prompts
|
|-- 02-prompts/
|   |-- resume-rewrite-prompt.md      # Master resume rewrite prompt
|   |-- job-market-scan-prompt.md     # Job market research prompt
|
|-- 03-research/
|   |-- job-market-scan-results.md    # 30+ postings + skills gap + recommendations
|
|-- 04-output/
|   |-- final-resume.md              # Rewritten resume (ready to format)
|   |-- ats-checklist-and-linkedin.md # Keywords, LinkedIn, top roles
|   |-- why-this-resume-works.md     # Design rationale
|
|-- README.md                         # This file
|-- how-to-regenerate.md             # Workflow & instructions
```
