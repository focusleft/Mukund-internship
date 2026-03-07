# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **documentation and workflow project** (not a software codebase). It contains a resume optimization pipeline targeting Software Robotics internships (Summer 2026), built by scanning 30+ real job postings and reverse-engineering a resume to match ATS and recruiter expectations.

There are no build steps, tests, linting, or CI/CD. All content is markdown and plain text processed through AI assistants.

## Repository Structure

- `01-original/` — Starting materials (original resume PDF + plain-text extraction)
- `02-prompts/` — Reusable AI prompts: `resume-rewrite-prompt.md` (master resume rewrite with market intelligence, keyword tiers, bullet examples) and `job-market-scan-prompt.md` (job market research prompt producing a 4-part report)
- `03-research/` — Output from running the scan prompt: 30+ postings, application guide, skills gap analysis, fine-tuning recommendations
- `04-output/` — Final deliverables: optimized resume, interview prep guide, ATS keyword checklist, LinkedIn content, design rationale
- `how-to-regenerate.md` — Step-by-step workflow for regenerating any part of the pipeline

## Workflow

```
01-original/original-resume.md
        |
        v
02-prompts/job-market-scan-prompt.md  →  03-research/job-market-scan-results.md
        |
        v
02-prompts/resume-rewrite-prompt.md  (informed by research Part 3 & 4)
        |
        v
04-output/final-resume.md + interview-prep.md + ats-checklist-and-linkedin.md
```

## Key Conventions

- All filenames use **kebab-case** (e.g., `final-resume.md`, not `final_resume.md`)
- Prompts in `02-prompts/` are self-contained — designed to be pasted into any AI assistant with the resume appended at the placeholder
- The job market scan prompt requires an AI with **web/search access** (Perplexity, ChatGPT with browsing)
- The resume rewrite prompt works with any AI assistant (Claude, ChatGPT, etc.)
- Metrics on the resume (e.g., "35% map consistency improvement", "45% query latency reduction") have corresponding justification cards in `04-output/interview-prep.md` — any metric change must be reflected in both files
- The resume is capped at **1 page** (candidate has <3 years experience)
- GPA is intentionally omitted (below 3.5 threshold)

## When Modifying Files

- If a resume bullet or metric changes in `final-resume.md`, update the matching card in `interview-prep.md`
- If new keywords are added, update the checklist in `ats-checklist-and-linkedin.md`
- If project titles change, update them in both `final-resume.md` and `resume-rewrite-prompt.md` (which has a title rename mapping table)
- Keep `README.md` links accurate if files are renamed or moved
