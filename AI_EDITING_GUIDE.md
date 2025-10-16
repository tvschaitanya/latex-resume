# AI Assistant Guide for Resume Editing

**Quick Reference:** This is a 3-file LaTeX resume template. You edit **ONLY** `data-resume.tex` by default. Contact info in `data-contact.tex` is private unless user explicitly grants access.

---

## PART 1: Template Structure

### The Three Files

**`data-contact.tex`** - PRIVATE (don't access by default)
```latex
\newcommand{\MyName}{John Doe}
\newcommand{\MyEmail}{email@example.com}
\newcommand{\MyPhone}{+1-555-123-4567}
\newcommand{\MyLinkedIn}{linkedin.com/in/username}
\newcommand{\MyGitHub}{github.com/username}
\newcommand{\MyPortfolio}{website.com}
```

**`data-resume.tex`** - YOUR MAIN EDITING TARGET
- Contains: Education, Experience, Projects, Skills, Certifications
- Section order controlled at bottom by `\resumeContent`

**`main.tex`** - DON'T EDIT (formatting only)

---

## PART 2: LaTeX Syntax Essentials

### Special Characters - MUST ESCAPE
```latex
& → \&     % → \%     $ → \$     # → \#     _ → \_
```

### Critical Rules
1. **Date ranges:** Always use `--` never `-`
   ```latex
   ✅ June 2020 -- Present
   ❌ June 2020 - Present
   ```

2. **Skills section:** Every line except last needs `\\`
   ```latex
   \textbf{Languages}{: Python, Java} \\
   \textbf{Tools}{: Git, Docker}      (no \\ on last line)
   ```

3. **Brackets must balance:** Every `{` needs a `}`

---

## PART 3: Section Templates

### Education
```latex
\resumeSubheading
  {University Name}{City, State}
  {Degree and Major, GPA: 3.8}{Aug. 2018 -- May 2022}
```

### Experience
```latex
\resumeSubheading
  {Job Title}{Start Date -- End Date}
  {Company Name}{City, State}
  \resumeItemListStart
    \resumeItem{Achievement with action verb and metrics}
    \resumeItem{Another achievement with impact}
  \resumeItemListEnd
```

### Projects
```latex
\resumeProjectHeading
  {\textbf{Project Name} $|$ \emph{Tech, Stack}}{Date -- Date}
  \resumeItemListStart
    \resumeItem{What you built and impact}
  \resumeItemListEnd
```

### Skills
```latex
\section{Technical Skills}
\begin{itemize}[leftmargin=0.15in, label={}]
  \small{\item{
   \textbf{Languages}{: Python, JavaScript, Java} \\
   \textbf{Frameworks}{: React, Django, Flask} \\
   \textbf{Tools}{: Git, Docker, AWS}
  }}
\end{itemize}
```

### Certifications
```latex
\resumeCertItem{\textbf{Certification Name}}{Issue Date}
```

---

## PART 4: Resume Writing Rules

### The 5 Core Principles

**1. Start with Action Verbs**
- Developed, Built, Implemented, Optimized, Led, Designed, Architected, Analyzed

**2. Always Quantify**
```latex
❌ Improved performance
✅ Improved performance by 60\%, reducing load time from 5s to 2s
```

**3. Show Impact, Not Tasks**
```latex
❌ Responsible for writing code
✅ Developed REST API handling 1M+ daily requests with 99.9\% uptime
```

**4. Be Specific with Tech**
```latex
❌ Built web app
✅ Built full-stack app using React, Node.js, PostgreSQL, and Docker
```

**5. Keep Bullets Concise** (1-2 lines max)

### ATS Optimization Checklist
- ✅ Use standard section names (Education, Experience, Skills)
- ✅ Include keywords from job description
- ✅ List exact technology names (JavaScript not JS)
- ✅ Use consistent date formats
- ✅ No images, graphics, or complex tables

---

## PART 5: Common Edits

### Reorder Sections
Edit bottom of `data-resume.tex`:
```latex
\newcommand{\resumeContent}{
  \experienceSection    % Change order by moving lines
  \skillsSection
  \projectsSection
  \educationSection
}
```

### Hide Section
Add `%` to comment out:
```latex
% \certificationsSection
```

### Add Experience Entry
Insert between `\resumeSubHeadingListStart` and `\resumeSubHeadingListEnd`:
```latex
\resumeSubheading
  {Software Engineer}{Jan. 2023 -- Present}
  {Tech Corp}{San Francisco, CA}
  \resumeItemListStart
    \resumeItem{Led development of microservices handling 2M+ requests daily}
    \resumeItem{Reduced deployment time by 70\% through CI/CD automation}
  \resumeItemListEnd
```

---

## PART 6: Privacy Rules

### Default Behavior
- ❌ **NEVER access** `data-contact.tex`
- ❌ **NEVER ask for** email, phone, or personal details
- ✅ **ONLY edit** `data-resume.tex`

### If User Asks About Contact Info
**Response:**
> "I don't have access to `data-contact.tex` to protect your privacy. You can update contact info there directly. Need help with resume content instead?"

### Exception: User Explicitly Grants Permission
Only if user says:
- "Can you edit my contact file?"
- "Here's my contact info, please add it"
- "I give you permission to access data-contact.tex"

**Then:**
1. Confirm: "Just to confirm, you're giving me permission to access your contact file?"
2. Wait for "yes"
3. Proceed with edit
4. Remind: "Done! I won't access this file again unless you explicitly ask."

---

## PART 7: Quick Validation

Before submitting edits:
- [ ] Special characters escaped (`&` → `\&`, `%` → `\%`)
- [ ] Date ranges use `--`
- [ ] Skills section: all lines except last have `\\`
- [ ] All brackets balanced
- [ ] Bullets start with action verbs
- [ ] Metrics included where possible
- [ ] Only edited `data-resume.tex` (unless permitted)
- [ ] No PII in content sections

---

## PART 8: Example Workflow

**User:** "Add my experience at Google"

**AI:**
"I'll add that to your experience section. To make it strong, I need:
1. Job title and dates
2. Key achievements (with metrics if possible)
3. Technologies you used

This helps me write impactful, ATS-friendly bullets!"

**User provides details**

**AI adds:**
```latex
\resumeSubheading
  {Senior Software Engineer}{June 2021 -- Aug. 2023}
  {Google}{Mountain View, CA}
  \resumeItemListStart
    \resumeItem{Developed scalable backend services using Go and gRPC, handling 10M+ daily requests}
    \resumeItem{Optimized database queries, reducing latency by 45\% for 5M+ users}
    \resumeItem{Mentored 3 junior engineers through code reviews and pair programming}
  \resumeItemListEnd
```

---

## Summary Card

| Task | File | Action |
|------|------|--------|
| Update email/phone | `data-contact.tex` | User edits (you don't access) |
| Add experience | `data-resume.tex` | Add `\resumeSubheading` block |
| Add project | `data-resume.tex` | Add `\resumeProjectHeading` block |
| Update skills | `data-resume.tex` | Edit skill categories |
| Reorder sections | `data-resume.tex` | Reorder in `\resumeContent` |
| Change formatting | `main.tex` | Don't edit (unless user requests) |

**Remember:** Your job is to help create strong, ATS-friendly content in `data-resume.tex` while respecting privacy in `data-contact.tex`.
