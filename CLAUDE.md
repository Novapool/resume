# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a LaTeX-based resume and cover letter repository with an AI-assisted tailoring workflow. The repository contains:

- **Master resume** (`Resume-Editing/master_resume.tex`): Superset archive and source of truth. Holds every experience, project, bullet variant, and skill, tagged by track. ~3 pages. Never submitted.
- **Track resumes** (`Resume-Editing/{software,aiml,it,sa}_resume.tex`): Four one-page starting points assembled from the superset, one per job type
- **Personality profile** (`personality.MD`): Personal background, interests, and context for cover letters
- **Resumes directory** (`Resumes/`): Job-specific tailored resume PDFs organized by company/role
- **Cover letters directory** (`CoverLetters/`): Job-specific cover letter PDFs organized by company/role
- **Research** (`research.md`): Resume best practices and industry insights

---

## Current Status (August 2026)

- **Recruiting for**: Summer 2027 internships. FAANG/big-tech applications for that cycle open July-October 2026; startups and mid-tier hire on a rolling basis through March-April
- **Graduation**: May 2027 (senior, completing a fifth year)
- **Tracks**: SWE/backend (primary), AI/ML + agentic (primary), IT/systems, solutions architect
- **In progress**: AWS SAA-C03, the clearest credential gap on the SA track
- Keep this block current. Stale dates here propagate into every cover letter.

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
5a. **Section order is fixed**: Education -> Experience -> Projects -> Leadership -> Skills, on all four tracks. `research.md` recommends a different order and has been explicitly overruled. Do not re-propose it. The SA resume is the one exception, adding a Summary above Education
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

## Content Integrity

Every number on these resumes has been audited once. Keep it that way.

**The bar**: a claim ships only if it can be derived out loud in an interview. Not "is it true" but "can it survive a follow-up question."

**Comment conventions in `master_resume.tex`:**
- `% VERIFY:` — on the resume but unconfirmed. Raise it before the resume ships; never silently promote it
- `% NOTE:` — deliberately cut, with the reason. A tombstone. Do not resurrect without new evidence

**Already cut, do not reintroduce**: "$50K annual losses prevented", "1,000+ concurrent rooms", "80% prediction accuracy". Each failed the defensibility bar.

**Confirmed**: Ember's 80%+ code reuse; AI Club's 500+ attendees / 90% retention / 4.8/5; the Pokemon agent's 93% vs scripted baselines and 747 rated ladder games; the CMA's 13.3% MAPE; GR Cup's R² = 0.631 over 3,257 laps.

**SoundSense placed 2nd at MHacks 2025.** It is not a win. Never write "Winner."

**Handle with care**: the Pokemon ladder win rate (~27% raw, ~19-23% contested; that project's own `MILESTONES.md` documents four corrections invalidating earlier numbers). Keep it off the resume.

---

## Positioning AI and Agentic Work (2026)

- Using Claude Code / Copilot / Cursor is **baseline**, not a differentiator. One skills-line mention, never its own bullet
- **Building** agent systems is the differentiator: orchestration, hooks, MCP, context and state management, evaluation harnesses. That earns a full project entry
- Never bury AI tooling in a generic list (`Tools: Git, Docker, Claude Code`). Give it its own skills category, or weave it into a bullet where it changed an outcome
- On backend/infra resumes, keep agentic work compressed. Leading with it dilutes the backend signal those teams hire for
- Evaluation discipline reads as senior and is rare: pre-registered success criteria, catching your own confounds, restating inflated numbers
- Over-polished, keyword-stuffed resumes are now a negative signal (Greenhouse 2026: 91% of hiring managers have caught or suspected AI-driven misrepresentation). The defense is artifacts, not adjectives

---

## Cover Letter Workflow

The cover letter lives in `master_cover_letter.tex` and uses the moderncv template (letter-only, no CV sections).

### Process
1. **Review source materials**:
   - `personality.MD`: Personal background, interests, technical experience, and motivations
   - `position.txt`: Job posting details, company information, and role requirements
2. **Edit master cover letter**: Work with `master_cover_letter.tex` to tailor content for specific job posting
3. **Compile to PDF**: Build using `pdflatex master_cover_letter.tex`
4. **Verify one page**: Check that letter fits on one page with closing on the same page
5. **Save to job directory**: Move final PDF to `CoverLetters/[JobName]/Laith_Assaf_CoverLetter.pdf`

### Input Files
- `personality.MD`: Personal context, technical background, interests, and career motivations
- `position.txt`: Job description and company-specific information
- `master_cover_letter.tex`: Master cover letter template using moderncv

### Cover Letter Rules

1. **No em dashes for continuing sentences** - use commas or periods instead. Em dashes (`---` in LaTeX) are only acceptable for hyphenated/compound words. Overuse reads as AI-generated.
2. **Always check page count after editing** - the letter must fit on one page with the closing on the same page.

### Reference Paragraph (the target voice)

This is the approved example of how a project should read in a cover letter. Match this register:

> I trained a Pokemon battle agent to a 93% win rate against scripted opponents using behavior cloning and PPO with MCTS at decision time. Then a review of my own evaluation harness showed the comparison was confounded: my search arm decoded greedily while the baseline sampled, which accounted for nearly the entire gain I'd been reporting. I restated the numbers and reopened two milestones. On the live ladder it still wins about 20% of contested games, and closing that gap is what I'm working on now.

**Why it works, and what to copy:**
- Every claim is checkable in both directions. Compare against the generic version: *"My Pokemon battle agent achieved a 93% win rate, showcasing my expertise in reinforcement learning."* Nobody can verify "showcasing my expertise," and every applicant writes it
- It names the specific technical failure (greedy vs.\ sampled decoding), not a vague "I learned a lot from my mistakes"
- It states the unfinished part plainly. Over-polished reads as fabricated in 2026; a real open problem does not
- It survives follow-up questions, because the details are real

**Rules for using this register:**
- **Once per letter**, inside the project paragraph. Never in the opening or the closing
- Used once it reads as confidence — being able to afford showing the ugly part. Used three times it reads as apologizing, and a cover letter is not the place to relitigate your own results
- Only applies where there is a real artifact behind it. Do not manufacture a self-criticism to sound authentic

---

### Cover Letter Guidelines

1. **Three-paragraph structure**:
   - **Paragraph 1**: Hook with genuine interest in company/role, brief background
   - **Paragraph 2**: Relevant experience and projects that align with role requirements
   - **Paragraph 3**: Why this company specifically, forward-looking close
2. **Authenticity**: Use real experiences and interests from `personality.MD` - no generic statements
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
- `personality.MD`: Personal background, interests, technical experience, and motivations for cover letters
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
5. **Keep `personality.MD` updated** with new projects, skills, and experiences