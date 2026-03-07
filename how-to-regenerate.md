# How to Regenerate & Finalize

Step-by-step instructions for regenerating any part of the pipeline and preparing the final resume for submission.

---

## Workflow

```
Step 1: Extract resume text
   01-original/original-resume.md

        |
        v

Step 2: Scan the job market
   02-prompts/job-market-scan-prompt.md  --->  03-research/job-market-scan-results.md

        |
        v

Step 3: Build the resume rewrite prompt (informed by research)
   02-prompts/resume-rewrite-prompt.md

        |
        v

Step 4: Generate the rewritten resume + supplementary outputs
   04-output/final-resume.md
   04-output/ats-checklist-and-linkedin.md
   04-output/why-this-resume-works.md
```

---

## Regenerate the Resume

1. Open `02-prompts/resume-rewrite-prompt.md`.
2. Copy the entire prompt (everything inside the ``` code block).
3. Paste into any AI assistant (Claude, ChatGPT, Perplexity).
4. Replace the `[PASTE THE CONTENTS OF resume.md HERE]` placeholder at the bottom with the contents of `01-original/original-resume.md`.
5. Run the prompt.
6. Save the output to `04-output/final-resume.md`.

---

## Refresh Job Market Data

1. Open `02-prompts/job-market-scan-prompt.md`.
2. Copy the entire prompt.
3. Paste into an AI assistant **with web/search access** (Perplexity recommended, or ChatGPT with browsing, or Google Gemini).
4. Run as-is — no modifications needed.
5. Save the output to `03-research/job-market-scan-results.md`.
6. Read Part 3 (Skills Gap Analysis) and Part 4 (Resume Fine-Tuning Recommendations) from the results.
7. Feed those findings back into `02-prompts/resume-rewrite-prompt.md` by updating the "Job Market Intelligence" section, keyword tiers, and bullet rewrite examples.
8. Re-run the resume rewrite prompt (see above) to produce an updated resume.

---

## Finalize the Resume for Submission

1. Open `04-output/final-resume.md`.
2. Replace all `[X%]` and `[X]` placeholders with real numbers from your projects.
3. Confirm the **Relevant Coursework** line matches courses you've actually taken.
4. Replace `github.com/mjeedigunta` with your real GitHub username.
5. Copy the content into a Word or Google Docs template.
6. Format using a clean, single-column layout with standard fonts (Calibri, Arial, or Times New Roman).
7. Export as both:
   - `.docx` — for ATS uploads (Workday, Greenhouse, Lever, Taleo)
   - `.pdf` — for direct sharing with recruiters and hiring managers
8. Name the file: `Mukund-Jeedigunta_Robotics_Intern_Resume.pdf`

---

## Update LinkedIn Profile

1. Open `04-output/ats-checklist-and-linkedin.md`.
2. Copy the **Suggested LinkedIn Headline** and paste it into your LinkedIn headline field.
3. Copy the **Suggested LinkedIn About Section** and paste it into your LinkedIn About field.

---

## Before You Submit — Checklist

- [ ] All `[X%]` and `[X]` placeholders replaced with real numbers
- [ ] Relevant Coursework matches courses actually taken
- [ ] GitHub username added to contact line
- [ ] LinkedIn headline updated
- [ ] LinkedIn About section updated
- [ ] Resume saved as both `.docx` and `.pdf`
- [ ] File named `Mukund-Jeedigunta_Robotics_Intern_Resume.pdf`
