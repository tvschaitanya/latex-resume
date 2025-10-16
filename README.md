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

---

## Need Help?

**For AI-assisted editing:** See `AI-EDITING-GUIDE.md`  
**For detailed instructions:** Check comments in each `.tex` file

---

## License

MIT License - Free to use and modify

**Credit:** Based on Jake Gutierrez's resume template
