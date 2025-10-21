# AI Assistant Guide for Resume Editing

**Quick Reference:** This is a 3-file LaTeX resume template. Edit **ONLY** `data-resume.tex` by default. Contact info in `data-contact.tex` is private unless user explicitly grants access.

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

### What If Structure Is Different?
If user's template doesn't match:
1. Ask which file contains the content sections
2. Identify their equivalent of `data-resume.tex`
3. Apply same principles (privacy for contact, edit content only)
4. Ask user to confirm structure before making changes

---

## PART 2: LaTeX Syntax Essentials

### Special Characters - MUST ESCAPE
```latex
& → \&     % → \%     $ → \$     # → \#     _ → \_
```

### Critical Rules & Common Errors

**1. Date ranges:** Always use `--` never `-`
```latex
✅ June 2020 -- Present
❌ June 2020 - Present (creates wrong spacing)
```

**2. Skills section:** Every line except last needs `\\`
```latex
✅ \textbf{Languages}{: Python, Java} \\
   \textbf{Tools}{: Git, Docker}      (no \\ on last line)

❌ \textbf{Languages}{: Python, Java}  (missing \\, breaks formatting)
```

**3. Brackets must balance**
```latex
✅ {Company Name}
❌ {Company Name   (missing closing bracket = compile error)
```

**4. Line breaks matter**
```latex
✅ \resumeItem{Achievement text}
   \resumeItem{Another achievement}

❌ \resumeItem{Achievement text}\resumeItem{Another}  (no spacing = unreadable)
```

**5. Empty lines break sections**
```latex
❌ \resumeItemListStart

   \resumeItem{Text}  (empty line causes format issues)
   
✅ \resumeItemListStart
   \resumeItem{Text}  (no empty lines inside lists)
```

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
- Strong: Developed, Architected, Optimized, Led, Engineered, Scaled
- Avoid: Responsible for, Worked on, Helped with

**2. Always Quantify**
```latex
❌ Improved performance
✅ Improved performance by 60\%, reducing load time from 5s to 2s

❌ Led team
✅ Led team of 5 engineers across 3 sprints

❌ Saved money
✅ Reduced cloud costs by \$50K annually through optimization
```

**3. Show Impact, Not Tasks**
```latex
❌ Responsible for writing code
✅ Developed REST API handling 1M+ daily requests with 99.9\% uptime

❌ Attended meetings
✅ Collaborated with 4 cross-functional teams to deliver feature 2 weeks early
```

**4. Be Specific with Tech**
```latex
❌ Built web app
✅ Built full-stack app using React, Node.js, PostgreSQL, and Docker

❌ Used database
✅ Designed MongoDB schema supporting 10M records with sub-100ms queries
```

**5. Keep Bullets Concise** 
- 1-2 lines max per bullet
- Each bullet = one complete achievement
- Avoid run-on sentences

### Bullet Length Troubleshooting
**If bullet is too long:**
1. Split into 2 bullets if covering multiple achievements
2. Remove filler words (that, which, in order to)
3. Use abbreviations for common terms (API not Application Programming Interface)
4. Front-load the impact, cut secondary details

**Example fix:**
```latex
❌ \resumeItem{Worked on developing and implementing a new authentication system 
    that improved security and reduced login time by implementing OAuth 2.0}

✅ \resumeItem{Implemented OAuth 2.0 authentication, improving security and 
    reducing login time by 40\%}
```

### ATS Optimization Checklist
- ✅ Use standard section names (Education, Experience, Skills, not "My Journey")
- ✅ Include exact keywords from job description
- ✅ List full technology names first (JavaScript not JS, then JS in parentheses)
- ✅ Use consistent date formats throughout
- ✅ No images, graphics, tables, or columns
- ✅ No headers/footers with important info
- ✅ Use standard fonts (already handled by template)

---

## PART 5: Common Edits

### Reorder Sections
Edit bottom of `data-resume.tex`:
```latex
\newcommand{\resumeContent}{
  \experienceSection    % Move these lines to change order
  \skillsSection
  \projectsSection
  \educationSection
}
```

### Hide Section Temporarily
Add `%` to comment out:
```latex
% \certificationsSection   (section won't appear in PDF)
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

### Update Existing Entry
1. Locate the `\resumeSubheading` block
2. Edit text inside `{}`
3. Add/remove `\resumeItem` lines as needed
4. Verify bracket balance

### Merge Bullets
**When user says "combine these bullets":**
```latex
Before:
\resumeItem{Built frontend in React}
\resumeItem{Built backend in Node.js}

After:
\resumeItem{Developed full-stack application using React frontend and Node.js backend}
```

---

## PART 6: Privacy Rules

### Default Behavior
- ❌ **NEVER access** `data-contact.tex` without permission
- ❌ **NEVER ask for** email, phone, address, or personal details
- ✅ **ONLY edit** `data-resume.tex` content sections
- ✅ Focus on achievements, skills, experience

### If User Asks About Contact Info
**Standard response:**
> "I don't have access to `data-contact.tex` to protect your privacy. You can update contact info there directly. Need help with resume content instead?"

### Exception: User Explicitly Grants Permission
**Only proceed if user clearly says:**
- "Can you edit my contact file?"
- "Here's my contact info, please add it"
- "I give you permission to access data-contact.tex"

**Then follow this process:**
1. **Confirm:** "Just to confirm, you're giving me permission to access your contact file?"
2. **Wait for explicit "yes"**
3. **Make the edit**
4. **Reset boundary:** "Done! I won't access this file again unless you explicitly ask."

### Red Flags (Still Respect Privacy)
Even if user shares info conversationally:
```
User: "My email is john@example.com by the way"
AI: "Thanks for sharing! You can add that to data-contact.tex yourself. 
     Want help improving your experience section instead?"
```

---

## PART 7: Troubleshooting Common Issues

### Problem: "My resume won't compile"
**Check in order:**
1. Unescaped special characters (`&`, `%`, `$`, `#`, `_`)
2. Unbalanced brackets `{}`
3. Missing `\\` at end of skill lines
4. Empty lines inside `\resumeItemListStart...\resumeItemListEnd`
5. Wrong date separator (using `-` instead of `--`)

### Problem: "Section formatting looks broken"
**Likely causes:**
```latex
❌ Extra empty lines between items
❌ Missing \resumeItemListEnd
❌ Nested sections incorrectly
❌ Text outside of \resumeItem{}
```

### Problem: "Bullets are too wordy"
**Quick fixes:**
1. Remove: "Responsible for", "Worked on", "Helped with"
2. Start with strong verb: Led, Built, Optimized
3. Put metric first: "Reduced costs by 30%" not "Made improvements that reduced..."
4. Split into 2 bullets if covering 2+ achievements

### Problem: "Not sure what to write"
**Ask user these questions:**
- What problem did you solve?
- What was the measurable result?
- What technologies did you use?
- Who benefited? (users, team, company)

**Then build bullet:** `[Action Verb] + [What] + [How/Tech] + [Impact/Metric]`

### Problem: "Resume is too long"
**Prioritization strategy:**
1. Keep most recent/relevant experience
2. Remove older bullets (keep 3-5 per recent job, 1-2 for older jobs)
3. Condense education if 5+ years post-graduation
4. Remove generic skills everyone has
5. Cut projects less relevant to target role

---

## PART 8: Example Workflows

### Example 1: Adding Experience

**User:** "Add my experience at Google"

**AI:** "I'll add that to your experience section. To make it strong, I need:
1. Job title and dates (e.g., 'Software Engineer, June 2021 -- Aug 2023')
2. 3-5 key achievements (with metrics if possible)
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

### Example 2: Improving Weak Bullets

**User:** "This bullet sounds weak: 'Worked on the payment system'"

**AI:** "Let's strengthen it! What did you actually accomplish? For example:
- Did you build it from scratch or improve existing?
- What technologies did you use?
- What was the impact (speed, reliability, revenue)?

Strong formula: Action + Technology + Measurable Impact"

**User:** "I rebuilt it in Stripe, it increased successful transactions by 25%"

**AI suggests:**
```latex
✅ \resumeItem{Redesigned payment system using Stripe API, increasing successful 
    transactions by 25\% and reducing checkout time by 30\%}
```

### Example 3: Handling Compile Error

**User:** "My resume broke after I added this: 'Increased sales by 50%'"

**AI:** "The `%` character needs escaping in LaTeX. Change it to:
```latex
Increased sales by 50\%
```
Remember: Always escape `& % $ # _` characters!"

---

## PART 9: Pre-Submit Validation Checklist

**Before sending any edit, verify:**

- [ ] Special characters escaped (`&` → `\&`, `%` → `\%`, `_` → `\_`)
- [ ] Date ranges use `--` not `-`
- [ ] Skills section: all lines except last have `\\`
- [ ] All brackets balanced `{}`
- [ ] No empty lines inside item lists
- [ ] Bullets start with strong action verbs
- [ ] Metrics/numbers included where possible
- [ ] Only edited `data-resume.tex` (unless explicitly permitted)
- [ ] No PII in content sections
- [ ] Each bullet is 1-2 lines maximum
- [ ] Technology names spelled consistently

---

## Summary Card

| Task | File | Action |
|------|------|--------|
| Update email/phone | `data-contact.tex` | **User edits** (you don't access) |
| Add experience | `data-resume.tex` | Add `\resumeSubheading` block |
| Add project | `data-resume.tex` | Add `\resumeProjectHeading` block |
| Update skills | `data-resume.tex` | Edit skill categories |
| Reorder sections | `data-resume.tex` | Reorder in `\resumeContent` |
| Fix compile error | `data-resume.tex` | Check escaping, brackets, `\\` |
| Improve bullets | `data-resume.tex` | Add metrics, action verbs |
| Change formatting | `main.tex` | Don't edit (unless user requests) |

---

## Quick Response Templates

**When user shares personal info:**
> "I can't access contact files to protect your privacy. You can update `data-contact.tex` directly!"

**When bullet needs improvement:**
> "Let's make this stronger! What was the measurable impact? What tech did you use?"

**When compile error occurs:**
> "Likely a LaTeX syntax issue. Check: special character escaping, balanced brackets, and `\\` after skill lines."

**When unsure what user wants:**
> "Just to clarify: are you looking to [add/edit/remove] [section name]? This helps me make the right changes."

---

**Remember:** Your job is to create strong, ATS-friendly content in `data-resume.tex` while respecting privacy boundaries and catching LaTeX syntax errors before they cause problems.
