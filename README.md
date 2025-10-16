# ATS-Friendly LaTeX Resume Template

A clean, professional resume template optimized for Applicant Tracking Systems.

## 📄 [View Sample Resume](Sample.pdf)

---

## Why Use This Template?

✅ **ATS-Compatible** - Machine-readable format that passes automated screening  
✅ **One-Page Layout** - Professional spacing, fits everything on one page  
✅ **Easy to Edit** - Content separated from formatting  
✅ **Privacy-Friendly** - Contact info stored separately  
✅ **Flexible** - Reorder or hide sections as needed

---

## Quick Start

### 1. Edit Your Information

**Contact Info** → Edit `data-contact.tex`
```latex
\newcommand{\MyName}{Your Name}
\newcommand{\MyEmail}{your.email@example.com}
\newcommand{\MyPhone}{+1-234-567-8900}
```

**Resume Content** → Edit `data-resume.tex`
- Education
- Experience  
- Projects
- Skills
- Certifications

### 2. Compile
```bash
pdflatex main.tex
```
Or upload to [Overleaf](https://www.overleaf.com) for online editing.

---

## File Structure

| File | Purpose | Edit? |
|------|---------|-------|
| `data-contact.tex` | Contact information (name, email, phone, links) | ✅ Yes |
| `data-resume.tex` | Resume content (all sections) | ✅ Yes |
| `main.tex` | Formatting & styling | ❌ No (unless changing design) |
| `AI_EDITING_GUIDE.md` | Instructions for AI assistants | 📖 Reference |
| `README.md` | This file - user documentation | 📖 Reference |

---

## Using AI Assistance

Want help tailoring your resume for a specific job? AI assistants can help optimize your content!

### What to Share with AI

**Give AI these 3 files:**
1. ✅ `AI_EDITING_GUIDE.md` - So AI understands the template structure
2. ✅ `data-resume.tex` - Your current resume content
3. ✅ **Job Description (JD)** - The job posting you're applying to

**Keep private (don't share with AI):**
- ❌ `data-contact.tex` - Contains your personal information

### Example Prompt

```
Hi! I need help tailoring my resume for a specific job. Here are the files:

1. AI_EDITING_GUIDE.md - Please read this first to understand the template structure
2. data-resume.tex - My current resume content
3. Job Description:
   [Paste the full job description here]

Please help me:
- Optimize my resume for this role
- Add relevant keywords from the JD
- Reorder sections if needed
- Improve bullet points to match job requirements
- Highlight relevant experience and skills
```

### What AI Can Help You With

**Content Optimization:**
- Write strong, ATS-friendly bullet points with action verbs
- Add quantifiable metrics and impact statements
- Match keywords from job description naturally
- Emphasize relevant experience for the target role

**Structure & Strategy:**
- Reorder sections based on job requirements
- Highlight most relevant skills first
- Suggest which experiences to emphasize
- Recommend what to add or remove

**ATS Optimization:**
- Include exact technology names from JD
- Use industry-standard terminology
- Ensure proper keyword density
- Maintain clean, parseable formatting

**Note:** The AI_EDITING_GUIDE.md includes privacy protections, so AI assistants won't ask for your contact information.

---

## Common Customizations

### Hide a Contact Field
Leave it blank:
```latex
\newcommand{\MyGitHub}{}  % GitHub won't appear
```

### Reorder Sections
Edit at bottom of `data-resume.tex`:
```latex
\newcommand{\resumeContent}{
  \experienceSection      % Put experience first
  \skillsSection
  \projectsSection
  \educationSection
}
```

### Hide a Section
Comment it out with `%`:
```latex
\newcommand{\resumeContent}{
  \educationSection
  \experienceSection
  % \certificationsSection  % Hidden
}
```

---

## Syntax Quick Reference

### Dates
Always use double dash:
```latex
✅ June 2020 -- Present
❌ June 2020 - Present
```

### Special Characters
Must be escaped:
```latex
& → \&    % → \%    $ → \$    # → \#    _ → \_
```

### Adding Experience
```latex
\resumeSubheading
  {Job Title}{Start Date -- End Date}
  {Company Name}{City, State}
  \resumeItemListStart
    \resumeItem{Achievement with metrics and impact}
    \resumeItem{Another achievement using action verbs}
  \resumeItemListEnd
```

### Adding Projects
```latex
\resumeProjectHeading
  {\textbf{Project Name} $|$ \emph{Tech Stack}}{Date Range}
  \resumeItemListStart
    \resumeItem{What you built and its impact}
  \resumeItemListEnd
```

### Skills Section
```latex
\textbf{Category}{: skill1, skill2, skill3} \\
\textbf{Another}{: more skills}  % Last line: no \\
```

---

## Requirements

- LaTeX distribution (TeX Live, MiKTeX, or Overleaf)
- FontAwesome5 package (for contact icons)

---

## Tips for Best Results

**Writing Strong Bullets:**
- Start with action verbs (Developed, Built, Optimized, Led)
- Include metrics (50% faster, 1M+ users, $100K saved)
- Be specific with technologies (React, PostgreSQL, AWS)
- Keep bullets 1-2 lines max

**ATS Optimization:**
- Use standard section names (Education, Experience, Skills)
- Include keywords from job descriptions
- Use exact technology names (JavaScript not JS)
- Keep formatting simple (no images or complex tables)

**Tailoring for Each Job:**
- Read the JD carefully and identify key requirements
- Match your experience to their needs
- Use their terminology and tech stack
- Reorder sections to highlight relevant experience first

---

## Workflow Example

1. **Save the job description** you're applying to
2. **Share with AI:** `AI_EDITING_GUIDE.md` + `data-resume.tex` + Job Description
3. **Get optimized content** tailored to the role
4. **Update** your `data-resume.tex` with AI suggestions
5. **Compile** to generate your tailored PDF
6. **Repeat** for each job application

---

## Need Help?

**For AI-assisted editing:** Share `AI_EDITING_GUIDE.md` + `data-resume.tex` + Job Description  
**For manual editing:** Check comments in each `.tex` file  
**For customization:** See the "Common Customizations" section above

---

## License

MIT License - Free to use and modify

**Credit:** Based on Jake Gutierrez's resume template
