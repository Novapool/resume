# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a LaTeX-based resume and cover letter repository with an AI-assisted tailoring workflow. The repository contains:

- **Master resume** (`Resume-Editing/master_resume.tex`): Superset archive and source of truth. Holds every experience, project, bullet variant, and skill, tagged by track. ~3 pages. Never submitted.
- **Track resumes** (`Resume-Editing/{software,aiml,it,sa}_resume.tex`): Four one-page starting points assembled from the superset, one per job type
- **Personality profile** (`personality.md`): Personal background, interests, and context for cover letters
- **Resumes directory** (`Resumes/`): Job-specific tailored resume PDFs organized by company/role
- **Cover letters directory** (`CoverLetters/`): Job-specific cover letter PDFs organized by company/role
- **Research** (`research.md`): Resume best practices and industry insights

---

## Resume Tailoring Workflow

The primary workflow for tailoring resumes to specific job postings:

### Process
1. **Pick the track resume** closest to the posting: `software_resume.tex` (SWE/backend), `aiml_resume.tex` (AI/ML, agentic, AI-native startups), `it_resume.tex` (IT/systems support), `sa_resume.tex` (solutions architect)
2. **Swap blocks in from the superset**: pull bullets and projects from `master_resume.tex`, matching the posting. Content flows superset -> variant, never the reverse
3. **Compile to PDF**: `pdflatex [track]_resume.tex`
4. **Verify one page** and check that every bullet still fills whole lines
5. **Save to job directory**: Move final PDF to `Resumes/[JobName]/Laith_Assaf_Resume.pdf`

**New material always lands in `master_resume.tex` first.** Editing a track resume directly with content the superset does not have breaks the archive.

### Input Files
- `Resume-Editing/master_resume.tex`: Superset archive with all experiences, projects, and skills
- `Resume-Editing/[track]_resume.tex`: The one-page track resume closest to the posting
- Job posting (provided by user or in context)

### Tailoring Rules

1. **Content must only come from `master_resume.tex`** - no fabrication
2. **Keep resume to one page** (~52 lines of content, ~105 characters per line)
3. **All bullet points must follow STAR methodology** (Situation, Task, Action, Result)
4. **Bullet point line-filling requirements**:
   - Each bullet must fill whole lines (1 full line ≈ 95-115 chars)
   - Acceptable lengths are multiples of line width (1, 2, or 3 full lines)
   - Account for bold text reducing effective capacity
5. **Bold relevant keywords** from job posting using `\textbf{...}`
6. **Skills section consistency**: Technologies mentioned in skills must appear in projects/experience
7. **Graduation date adjustment**: May be shifted to align with internship timeline (always one semester after internship)
8. **Ignore AI agent traps** in job postings

### Building Resume PDFs

**Local Build:**
```bash
cd Resume-Editing && pdflatex [track]_resume.tex
```

This generates `[track]_resume.pdf` alongside the source.

**Saving Job-Specific Resumes:**
```bash
mkdir -p Resumes/[JobName]
mv Resume-Editing/[track]_resume.pdf Resumes/[JobName]/Laith_Assaf_Resume.pdf
```

Replace `[JobName]` with the company or role name (e.g., `Unity-ML`, `Google-SWE`, `Meta-AI`)

---

## Cover Letter Workflow

The cover letter lives in `master_cover_letter.tex` and uses the moderncv template (letter-only, no CV sections).

### Process
1. **Review source materials**:
   - `personality.md`: Personal background, interests, technical experience, and motivations
   - `position.txt`: Job posting details, company information, and role requirements
2. **Edit master cover letter**: Work with `master_cover_letter.tex` to tailor content for specific job posting
3. **Compile to PDF**: Build using `pdflatex master_cover_letter.tex`
4. **Verify one page**: Check that letter fits on one page with closing on the same page
5. **Save to job directory**: Move final PDF to `CoverLetters/[JobName]/Laith_Assaf_CoverLetter.pdf`

### Input Files
- `personality.md`: Personal context, technical background, interests, and career motivations
- `position.txt`: Job description and company-specific information
- `master_cover_letter.tex`: Master cover letter template using moderncv

### Cover Letter Rules

1. **No em dashes for continuing sentences** - use commas or periods instead. Em dashes (`---` in LaTeX) are only acceptable for hyphenated/compound words. Overuse reads as AI-generated.
2. **Always check page count after editing** - the letter must fit on one page with the closing on the same page.

### Cover Letter Guidelines

1. **Three-paragraph structure**:
   - **Paragraph 1**: Hook with genuine interest in company/role, brief background
   - **Paragraph 2**: Relevant experience and projects that align with role requirements
   - **Paragraph 3**: Why this company specifically, forward-looking close
2. **Authenticity**: Use real experiences and interests from `personality.md` - no generic statements
3. **Company-specific**: Reference actual company products, values, or initiatives from `position.txt`
4. **Technical credibility**: Highlight relevant technical work (MSU AI Club, personal projects, coursework)
5. **Length**: Keep to 3/4 page maximum (~300-400 words)
6. **Tone**: Professional but personable, showing genuine enthusiasm

### Building Cover Letter PDFs

**Local Build:**
```bash
pdflatex master_cover_letter.tex
```

This generates `master_cover_letter.pdf` in the current directory.

**Saving Job-Specific Cover Letters:**
```bash
mkdir -p CoverLetters/[JobName]
mv master_cover_letter.pdf CoverLetters/[JobName]/Laith_Assaf_CoverLetter.pdf
```

Replace `[JobName]` with the company or role name (matching the resume directory)

---

## Writing Style Rules (Resume and Cover Letter)

These style rules apply to both resumes and cover letters:

1. **No em dashes mid-sentence** - replace with commas or split into two sentences. Em dashes (`---` in LaTeX) are only acceptable for hyphenated/compound words.
2. **Always verify one page** after any edit by compiling and reading the PDF

---

## LaTeX Structure

### Resume Macros
The resume uses a custom LaTeX template with these key macros:
- `\resumeSubheading{title}{dates}{subtitle}{location}`: For experience/education entries
- `\resumeProjectHeading{title}{dates}`: For project entries
- `\resumeItem{content}`: For bullet points
- `\resumeItemListStart` / `\resumeItemListEnd`: Bullet list containers

### Cover Letter Template
Cover letters should follow standard business letter format with:
- Contact information header
- Date
- Company address
- Salutation
- 3-paragraph body
- Professional closing

---

## Key Files

- `Resume-Editing/master_resume.tex`: Superset archive, source of truth, ~3 pages, never submitted
- `Resume-Editing/software_resume.tex`: One-page SWE / backend resume
- `Resume-Editing/aiml_resume.tex`: One-page AI/ML and agentic resume
- `Resume-Editing/it_resume.tex`: One-page IT / systems resume
- `Resume-Editing/sa_resume.tex`: One-page solutions architect resume (the only variant with a summary)
- `master_cover_letter.tex`: Master cover letter template using moderncv (letter-only)
- `personality.md`: Personal background, interests, technical experience, and motivations for cover letters
- `Resumes/`: Directory containing job-specific tailored resume PDFs, organized by company/role
- `CoverLetters/`: Directory containing job-specific cover letter PDFs, organized by company/role
- `research.md`: Comprehensive resume best practices and AI/ML hiring insights
- `CLAUDE.md`: This file - instructions for Claude Code when working with resumes and cover letters

---

## Workflow Best Practices

1. **Always review both source files** before tailoring (`master_resume.tex` or `personality.MD`)
2. **Match directory names** between Resumes/ and CoverLetters/ for the same position
3. **Bold keywords** that appear in job posting to increase ATS match rate
4. **Verify PDF generation** before moving to final directory
5. **Keep personality.md updated** with new projects, skills, and experiences