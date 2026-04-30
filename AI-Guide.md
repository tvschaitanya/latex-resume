# AI Guide: Updating the Modular LaTeX Resume

## Project Overview

This is a modular LaTeX resume system built with three files:

| File             | Purpose                                               | Should AI touch it?                 |
| ---------------- | ----------------------------------------------------- | ----------------------------------- |
| main.tex         | Layout engine, formatting, custom commands            | No — unless user explicitly asks    |
| data-contact.tex | User personal info (name, email, phone, website)      | Never read or write                 |
| data-resume.tex  | Resume content (summary, experience, education, etc.) | Yes — this is the only file to edit |

---

## AI Role in This System

The AI is a **resume content editor only**.

It:

- Reads `data-resume.tex`
- Applies requested updates
- Returns a fully updated `data-resume.tex`

It does NOT:

- Modify layout (`main.tex`)
- Modify contact info (`data-contact.tex`)
- Change LaTeX system or formatting rules

---

## AI Workflow Instructions (IMPORTANT)

When updating the resume:

1. Use this guide only to understand structure and rules.
2. The user must provide:
   - Current `data-resume.tex`
   - New data or requested changes

3. The AI will ONLY modify `data-resume.tex`.
4. The AI must return a complete updated `data-resume.tex`.
5. The AI must NOT:
   - Modify `main.tex`
   - Modify `data-contact.tex`
   - Create new LaTeX commands
   - Change formatting or layout rules

---

## AI Readiness Protocol (IMPORTANT)

After reading and understanding this file, the AI must:

- Confirm it is ready
- Ask for required inputs

Required inputs:

- Current `data-resume.tex`
- New updates or changes

Example response:
I’m ready. Please provide your current data-resume.tex file and the changes you want applied, and I’ll update it for you.

The AI must not make any changes until both inputs are provided.

---

## The Only File You Edit: data-resume.tex

All resume content is stored in LaTeX macros inside this file.

Each section is a `\newcommand` block.

---

## Section Order Control

Bottom of `data-resume.tex` controls output order:

\summarySection
\skillsSection
\experienceSection
\projectsSection
\educationSection

To reorder sections:

- Only change order of these lines
- Do not modify macro definitions

---

## Helper Commands Reference

These come from main.tex and must NOT be changed.

### \resumeSubheading (Jobs / Education)

\resumeSubheading
{Organization Name}{Location}
{Role / Degree}{Date Range}

---

### \resumeItem (Bullets with label)

\resumeItem{Label}
{Description}

---

### \resumeItemPlain (Bullets without label)

\resumeItemPlain{Text here}

---

### \resumeSubItem (Projects / Skills)

\resumeSubItem{Name}{Description}

---

### List Wrappers

\resumeSubHeadingListStart
...
\resumeSubHeadingListEnd

\resumeItemListStart
...
\resumeItemListEnd

---

## Section Structures

### Summary

\newcommand{\summarySection}{
\section{Summary}
\small{
Your summary text here.
}\vspace{-5pt}
}

Keep it 2–4 sentences.

---

### Education

\newcommand{\educationSection}{
\section{Education}
\resumeSubHeadingListStart
\resumeSubheading
{University}{City, State}
{Degree; GPA}{Date}
\resumeSubHeadingListEnd
}

Most recent first.

---

### Experience

\newcommand{\experienceSection}{
\section{Experience}
\resumeSubHeadingListStart

\resumeSubheading
{Company}{Location}
{Title}{Dates}

\resumeItemListStart
\resumeItem{Work}
{Description}
\resumeItemListEnd

\resumeSubHeadingListEnd
}

Most recent first.

---

### Projects

\newcommand{\projectsSection}{
\section{Projects}
\resumeSubHeadingListStart

\resumeSubItem{Project Name}
{Description + tech stack}

\resumeSubHeadingListEnd
}

---

### Skills

\newcommand{\skillsSection}{
\section{Skills}
\resumeSubHeadingListStart

\resumeSubItem{Category}{Items}

\resumeSubHeadingListEnd
}

---

## Rules to Always Follow

1. Never touch data-contact.tex
2. Never modify main.tex
3. Only edit data-resume.tex
4. Do not create new commands
5. Preserve all structure and formatting
6. Keep section order unless user requests change
7. Most recent entries go first
8. Return full updated file every time

---

## Common Tasks

Add job → add \resumeSubheading in Experience
Add bullet → add \resumeItem
Add project → add \resumeSubItem
Add skill → add \resumeSubItem
Add education → add \resumeSubheading
Update summary → edit text inside \small{}
Reorder sections → change bottom order only
