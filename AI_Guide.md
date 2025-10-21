# AI Guide: LaTeX Resume Editor

You are helping edit a LaTeX-based resume system. Follow these instructions precisely.

---

## File Structure (CRITICAL)

**data-contact.tex** → PRIVATE. Never request, view, or reference this file.

**data-resume.tex** → YOUR ONLY EDITING FILE. All content lives here.

**main.tex** → Template/formatting only. Don't edit unless explicitly requested.

---

## LaTeX Commands You'll Use

### Experience/Education

```latex
\resumeSubheading
  {Job Title/Degree}{Date Range}
  {Company/School}{Location}
  \resumeItemListStart
    \resumeItem{Achievement bullet}
  \resumeItemListEnd
```

### Projects

```latex
\resumeProjectHeading
  {\textbf{Project Name} $|$ \emph{Tech1, Tech2}}{Date Range}
  \resumeItemListStart
    \resumeItem{What you built}
  \resumeItemListEnd
```

### Skills

```latex
\begin{itemize}[leftmargin=0.15in, label={}]
  \small{\item{
   \textbf{Category}{: item1, item2, item3} \\
   \textbf{Another}{: item1, item2}
  }}
\end{itemize}
```

### Certifications

```latex
\resumeCertItem{\textbf{Full Certification Name}}{Month Year}
```

---

## LaTeX Syntax Rules

- Special characters: `Texas A\&M` (use `\&`)
- Date ranges: `--` (two hyphens, not one)
- Pipe symbols: `$|$`
- Bold: `\textbf{text}`
- Italics: `\emph{text}`

### Date Format (CRITICAL)

**✓ CORRECT:** `June 2020 -- Present`, `Aug 2018 -- May 2021`, `January 2024`

**✗ WRONG:** `Jun. 2020`, `Apr. 2025`, `6/2020`, `January 2019 - March 2020`

**Rules:**

- Full month names OR abbreviations WITHOUT periods
- Always use `--` for ranges (not single `-`)
- Capitalize "Present"

---

## Resume Writing Framework

### Every Bullet Must Have:

1. **Action Verb** (Developed, Implemented, Optimized, Led)
2. **What You Did** (specific technical detail)
3. **Quantifiable Result** (numbers, percentages, scale)

**Formula:** [Action Verb] + [Technical Detail] + [Quantified Impact]

### Example Transformation

**WEAK:** "Worked on backend features"

**STRONG:** "Developed RESTful APIs using Python and Flask serving 10K+ daily users, reducing response time by 40%"

### Action Verbs by Category

- **Build:** Developed, Engineered, Built, Implemented, Designed, Architected
- **Improve:** Optimized, Enhanced, Streamlined, Reduced, Increased, Accelerated
- **Lead:** Led, Managed, Mentored, Coordinated, Directed
- **Fix:** Resolved, Debugged, Troubleshot, Migrated
- **Analyze:** Researched, Evaluated, Investigated, Analyzed

### Quantification Examples

- Numbers: "200+ printers", "50K+ lines", "team of 8"
- Percentages: "reduced by 40%", "improved by 25%"
- Scale: "enterprise-level", "10K+ users"
- Time: "delivered in 2 weeks"
- Quality: "99.9% uptime", "4.5/5 rating"

---

## ATS Optimization

**Include Keywords:**

- Exact terms from job descriptions
- Technologies: Python, React, AWS, Docker, Kubernetes
- Methodologies: Agile, CI/CD, REST API, Microservices
- Certifications: spell out full names

**Avoid:**

- Abbreviations without context
- Generic phrases like "responsible for"
- Weak verbs like "helped with", "worked on"

---

## Tailoring Resume to Job Description

When user provides a job description:

1. **Extract Keywords**

   - Required skills and technologies
   - Preferred qualifications
   - Responsibilities mentioned
   - Industry-specific terms

2. **Prioritize Matching Experience**

   - Lead with most relevant roles
   - Emphasize matching technologies in bullets
   - Add specific keywords naturally

3. **Rewrite Bullets to Match**

   - If job wants "microservices" → highlight microservices work
   - If job wants "mentoring" → emphasize leadership bullets
   - If job wants "AWS" → detail AWS services used

4. **Update Skills Section**

   - Move matching skills to front of categories
   - Add any relevant skills you have that match the job

5. **Customize Summary**
   - Mirror the job title in your summary
   - Include 2-3 key requirements from the job description
   - Keep it under 4 sentences

**Example:**
Job wants: "Senior Python Engineer with AWS and PostgreSQL experience"

Tailor by:

- Summary starts: "Senior Software Engineer specializing in Python..."
- First experience bullet mentions Python, AWS, PostgreSQL
- Skills section lists Python first, prominently features AWS services
- Projects highlight Python/AWS stack

---

## Section Examples

### Experience (Strong)

```latex
\resumeSubheading
  {Backend Software Engineer}{June 2021 -- March 2023}
  {Tech Corp}{San Francisco, CA}
  \resumeItemListStart
    \resumeItem{Engineered microservices using Python and FastAPI handling 500K+ requests/day with 99.9\% uptime}
    \resumeItem{Optimized PostgreSQL queries reducing average response time by 45\% and improving user experience}
    \resumeItem{Mentored 3 junior engineers in test-driven development and conducted 100+ code reviews}
  \resumeItemListEnd
```

### Project (Strong)

```latex
\resumeProjectHeading
  {\textbf{E-Commerce Platform} $|$ \emph{React, Node.js, MongoDB, AWS}}{Jan 2023 -- Present}
  \resumeItemListStart
    \resumeItem{Built full-stack platform processing 1K+ daily transactions with Stripe integration}
    \resumeItem{Implemented JWT authentication and role-based access control for 5K+ users}
    \resumeItem{Deployed on AWS with CI/CD pipeline achieving 99.9\% uptime}
  \resumeItemListEnd
```

### Skills (Strong)

```latex
\section{Technical Skills}
\begin{itemize}[leftmargin=0.15in, label={}]
  \small{\item{
   \textbf{Languages}{: Python, JavaScript/TypeScript, Java, SQL, C++, HTML/CSS} \\
   \textbf{Frameworks}{: React, Node.js, Flask, FastAPI, Spring Boot, Express} \\
   \textbf{Tools}{: Docker, Kubernetes, Git, Jenkins, AWS (EC2, S3, Lambda), GCP} \\
   \textbf{Databases}{: PostgreSQL, MongoDB, Redis, MySQL}
  }}
\end{itemize}
```

### Summary (Strong)

```latex
\section{Summary}
\begin{itemize}[leftmargin=0.15in, label={}]
  \small{\item{
    Full-Stack Software Engineer with 4+ years building scalable applications using Python, React, and AWS. Proven track record delivering production systems serving 100K+ users with 99.9\% uptime. Expertise in microservices architecture, CI/CD pipelines, and cloud infrastructure. AWS Certified Solutions Architect with experience leading cross-functional teams.
  }}
\end{itemize}
```

---

## Your Workflow

When user provides their resume info + job description:

1. **Analyze job description** for keywords and requirements
2. **Review their current content** in data-resume.tex
3. **Rewrite/reorder** to emphasize matching experience
4. **Add quantifiable metrics** wherever possible
5. **Output complete section** ready to paste into data-resume.tex
6. **Briefly explain** what you changed and why

---

## Final Checklist

- [ ] Strong action verbs start each bullet
- [ ] Every bullet has quantifiable impact
- [ ] Dates formatted correctly (no periods, use `--)
- [ ] Job-specific keywords included naturally
- [ ] LaTeX syntax is correct (braces, special chars)
- [ ] Most relevant experience emphasized first
- [ ] No repetition across bullets
- [ ] Proper nesting of ListStart/ListEnd

---

## Remember

- Never ask about or reference data-contact.tex
- Focus on impact, not just responsibilities
- Every word must earn its place
- Tailor ruthlessly to the job description
- Output valid LaTeX ready to compile
