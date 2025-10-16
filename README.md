# ATS-Friendly Resume Template

A clean, professional LaTeX resume template optimized for Applicant Tracking Systems (ATS).

## Features

- ✅ **ATS-Compatible** - Machine-readable, properly formatted for automated parsing
- ✅ **One-Page Format** - Optimized spacing to fit all content on a single page
- ✅ **Professional Design** - Times New Roman, 11pt, 0.5" margins
- ✅ **Easy to Edit** - Separated content from formatting for simple updates
- ✅ **Flexible Sections** - Reorder or hide sections as needed

## Files

- **`data-contact.tex`** - Your personal contact information
- **`data-resume.tex`** - Your resume content (education, experience, projects, skills, certifications)
- **`main.tex`** - Document formatting (do not edit unless changing styles)

## Quick Start

1. **Edit your contact info** in `data-contact.tex`
2. **Edit your resume content** in `data-resume.tex`
3. **Compile** `main.tex` to generate your PDF

## Customization

### Hide a contact field
Leave it blank in `data-contact.tex`:
```latex
\newcommand{\MyGitHub}{}
```

### Reorder sections
Change the order in `data-resume.tex` under "SECTION ORDER":
```latex
\newcommand{\resumeContent}{
  \skillsSection
  \experienceSection
  \educationSection
  \projectsSection
  \certificationsSection
}
```

### Hide a section
Comment it out with `%`:
```latex
\newcommand{\resumeContent}{
  \educationSection
  \experienceSection
  % \certificationsSection  <- This section won't appear
}
```

## Requirements

- LaTeX distribution (TeX Live, MiKTeX, or Overleaf)
- FontAwesome5 package (for icons)

## Compilation

```bash
pdflatex main.tex
```

Or use Overleaf for online editing.

## Template Structure

**Education & Experience entries:**
```latex
\resumeSubheading
  {Position/Degree}{Location}
  {Company/Institution}{Date Range}
```

**Project entries:**
```latex
\resumeProjectHeading
  {\textbf{Project Name} $|$ \emph{Technologies}}{Date Range}
```

**Certification entries:**
```latex
\resumeCertItem{Certification Name}{Date}
```

## License

MIT License - Based on Jake Gutierrez's resume template
