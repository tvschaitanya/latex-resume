# AI Assistant Guide for Resume Editing

This guide helps AI models understand and edit the resume template correctly.

## Template Overview

This is a 3-file LaTeX resume template:
- `data-contact.tex` - Contact information
- `data-resume.tex` - Resume content
- `main.tex` - Formatting (do not modify)

## File Locations & Purposes

### data-contact.tex
**Purpose:** Store personal contact information  
**Editable:** YES - Users update this frequently  
**Variables:**
```latex
\newcommand{\MyName}{Full Name}
\newcommand{\MyPhone}{Phone Number}
\newcommand{\MyEmail}{email@example.com}
\newcommand{\MyLinkedIn}{linkedin.com/in/username}
\newcommand{\MyGitHub}{github.com/username}
\newcommand{\MyPortfolio}{website.com}
```

### data-resume.tex
**Purpose:** Store all resume content  
**Editable:** YES - Main content editing happens here  
**Sections:** Education, Experience, Projects, Skills, Certifications

### main.tex
**Purpose:** Formatting and document structure  
**Editable:** NO - Only edit for style changes

## AI Editing Instructions

### When user asks to update contact info:
**Edit:** `data-contact.tex`  
**Action:** Update the relevant `\newcommand` with new value  
**Example:**
```latex
\newcommand{\MyEmail}{newemail@example.com}
```

### When user asks to add/edit work experience:
**Edit:** `data-resume.tex`  
**Location:** Inside `\experienceSection`  
**Format:**
```latex
\resumeSubheading
  {Job Title}{Start Date -- End Date}
  {Company Name}{City, State}
  \resumeItemListStart
    \resumeItem{Achievement or responsibility description}
    \resumeItem{Another achievement with metrics when possible}
  \resumeItemListEnd
```

### When user asks to add/edit education:
**Edit:** `data-resume.tex`  
**Location:** Inside `\educationSection`  
**Format:**
```latex
\resumeSubheading
  {University Name}{City, State}
  {Degree and Major}{Start Date -- End Date}
```

### When user asks to add/edit projects:
**Edit:** `data-resume.tex`  
**Location:** Inside `\projectsSection`  
**Format:**
```latex
\resumeProjectHeading
  {\textbf{Project Name} $|$ \emph{Tech Stack}}{Date Range}
  \resumeItemListStart
    \resumeItem{Project description and impact}
  \resumeItemListEnd
```

### When user asks to add/edit certifications:
**Edit:** `data-resume.tex`  
**Location:** Inside `\certificationsSection`  
**Format:**
```latex
\resumeCertItem{Certification Name}{Issue Date}
```

### When user asks to update skills:
**Edit:** `data-resume.tex`  
**Location:** Inside `\skillsSection`  
**Format:**
```latex
\textbf{Category}{: skill1, skill2, skill3} \\
```

### When user asks to reorder sections:
**Edit:** `data-resume.tex`  
**Location:** In `\resumeContent` command at the bottom  
**Action:** Reorder the section commands

### When user asks to hide a section:
**Edit:** `data-resume.tex`  
**Location:** In `\resumeContent` command  
**Action:** Comment out with `%`

## Important LaTeX Syntax Rules

1. **Special characters require escaping:**
   - `&` → `\&`
   - `%` → `\%`
   - `$` → `\$`
   - `#` → `\#`

2. **Date ranges use double dash:** `--`
   ```latex
   Aug. 2020 -- May 2024
   ```

3. **Italics use:** `\emph{text}`

4. **Bold uses:** `\textbf{text}`

5. **Bullet points use:** `\resumeItem{text}`

## Common User Requests & Responses

**"Add my work experience"**
→ Edit `data-resume.tex`, add to `\experienceSection`

**"Update my email"**
→ Edit `data-contact.tex`, change `\MyEmail`

**"Remove certifications section"**
→ Edit `data-resume.tex`, comment out `\certificationsSection` in `\resumeContent`

**"Put skills section first"**
→ Edit `data-resume.tex`, move `\skillsSection` to top in `\resumeContent`

**"Change font or margins"**
→ This requires editing `main.tex` (advanced users only)

## Validation Checklist

Before returning edited files, verify:
- [ ] All LaTeX special characters are escaped
- [ ] Date ranges use `--` not `-`
- [ ] Brackets `{}` are balanced
- [ ] Commands are spelled correctly
- [ ] Spacing and indentation maintained
- [ ] Only edited the requested file(s)

## Error Prevention

**DON'T:**
- Mix up the file locations
- Edit `main.tex` for content changes
- Forget to escape special characters
- Use single dash `-` for date ranges
- Break the LaTeX syntax structure

**DO:**
- Keep formatting consistent with existing entries
- Maintain proper indentation
- Use the exact command names
- Preserve the structure
- Test that brackets are balanced
