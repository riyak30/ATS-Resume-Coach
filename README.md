# ATS Resume Coach

## Build Summary

### Problem or Skill Addressed

Most job seekers submit resumes without knowing whether they will pass an Applicant Tracking System (ATS) — the automated software that employers use to filter candidates before a human ever reads the application. ATS systems score resumes based on keyword matching, formatting structure, and content alignment with a specific job description. Resumes that fail this initial screen are rejected automatically, even when the candidate is qualified.

This project addresses the skill of resume optimization: specifically, how to tailor a resume to a job description in a way that improves ATS compatibility, surfaces keyword gaps, and strengthens the quality of bullet point writing.

---

### Who It Helps

- **Early-career job seekers and students** who are applying to their first internships or full-time roles and are unfamiliar with ATS filtering.
- **Career changers** who need to reframe their existing experience using industry-specific language from a new field.
- **Active job seekers** who are applying to many roles and want fast, actionable feedback on how well each tailored resume matches a given posting.
- **Anyone** who has ever sent out dozens of applications and heard nothing back — and wants to understand why.

---

### How It Works

The app is a single HTML file that runs entirely in the browser with no backend, no login, and no external API calls.

**User Flow:**

1. **Upload a resume** — The user drags and drops (or clicks to select) their resume file in PDF, DOCX, or TXT format. The file is parsed client-side using PDF.js (for PDFs) and Mammoth.js (for DOCX files).

2. **Paste a job description** — The user copies the full job posting text into a text area. The engine splits it into required vs. preferred qualifications sections for more accurate analysis.

3. **Click Analyze** — The rule-based analysis engine runs locally in the browser and produces five structured outputs in a few seconds:

   - **ATS Match Score** — A weighted score (0–100) based on keyword coverage, formatting quality, and bullet strength. Displayed as a color-coded progress bar with a letter grade.
   - **Keyword Gap Analysis** — Terms and phrases from the job description that are missing from the resume, ranked by criticality (required vs. preferred).
   - **Formatting Risks** — Heuristic checks that flag common ATS failure points: missing contact fields, use of tables or graphics, lack of standard section headers, file-type issues, and more.
   - **Bullet Point Rewrites** — The weakest resume bullets are identified by scoring them for specificity, action verb strength, and measurable outcomes. Each weak bullet is rewritten using a results-oriented template.
   - **Quick Wins** — A prioritized list of the five highest-impact changes the user can make right now to improve their score.

**No data ever leaves the user's device.** All parsing and analysis happens in the browser using JavaScript.

---

### Why It Matters

Resume optimization is one of the most high-leverage skills a job seeker can develop, yet it is rarely taught directly. Most people learn through trial and error — submitting applications, getting no response, and not knowing why. This tool closes that feedback loop.

**How it improves learning:**
- It makes the invisible visible. Users can see exactly which keywords are missing and why that matters.
- It teaches resume writing patterns by example — the bullet rewrite feature shows side-by-side before/after transformations that model stronger writing habits over time.
- It builds awareness of ATS mechanics, helping users internalize what "tailoring a resume" actually means in practice rather than as an abstract recommendation.

**How it improves readiness:**
- Users can run a resume through the tool against any job posting in under a minute, making it practical to optimize for every application rather than sending a generic resume.
- The quick wins section provides a clear action checklist that removes ambiguity — users know exactly what to fix and in what order.
- By improving match scores before submission, users increase the probability that their resume reaches a human recruiter, which is the actual goal of every application.

---

### Technical Notes

- **Stack:** Vanilla HTML, CSS, JavaScript — no build tools, no frameworks, no dependencies beyond two CDN libraries (PDF.js, Mammoth.js)
- **Deployment:** Single file, deployable to GitHub Pages with zero configuration
- **Analysis engine:** Fully local, rule-based — keyword frequency scoring, JD section parsing, formatting heuristics, bullet quality scoring, and template-based rewriting
