# AI Guide: Updating the Modular LaTeX Resume

## Project Overview

This is a modular LaTeX resume with three files:

| File               | Purpose                                               | Should AI touch it?                               |
| ------------------ | ----------------------------------------------------- | ------------------------------------------------- |
| `main.tex`         | Layout engine, formatting, custom commands            | ❌ No — unless user explicitly asks               |
| `data-contact.tex` | User's personal info (name, email, phone, website)    | 🚫 Never read or write — user edits this manually |
| `data-resume.tex`  | Resume content (summary, experience, education, etc.) | ✅ Yes — this is the only file to edit            |

---

## The Only File You Edit: `data-resume.tex`

All resume content lives inside LaTeX **macros** (commands). Each section is a `\newcommand` block. You fill in content inside those blocks using the helper commands defined in `main.tex`.

### Section Order

The order sections appear in the PDF is controlled at the **bottom** of `data-resume.tex`:

```latex
\summarySection
\skillsSection
\experienceSection
\projectsSection
\educationSection
```

To reorder sections, just reorder these lines. Do not add or remove a line unless the user adds or removes a whole section.

---

## Helper Commands Reference

These are defined in `main.tex`. Use them exactly as shown — do not invent new ones.

### `\resumeSubheading` — Job or Degree heading

```latex
\resumeSubheading
  {Organization Name}{Location}
  {Role / Degree Title}{Date Range}
```

### `\resumeItem` — Bullet point with a bold label

```latex
\resumeItem{Label}
  {Description of what you did or built.}
```

### `\resumeItemPlain` — Bullet point without a label

```latex
\resumeItemPlain{Plain bullet text here.}
```

### `\resumeSubItem` — Used in Projects and Skills sections

```latex
\resumeSubItem{Item Name}{Short description.}
```

### List wrappers — Always wrap subheadings and items in these

```latex
\resumeSubHeadingListStart
  ... \resumeSubheading blocks go here ...
\resumeSubHeadingListEnd
```

```latex
\resumeItemListStart
  ... \resumeItem or \resumeItemPlain blocks go here ...
\resumeItemListEnd
```

---

## How Each Section Is Structured

### Summary

```latex
\newcommand{\summarySection}{%
  \section{Summary}
  \small{
    Your summary text here.
  }\vspace{-5pt}
}
```

- Just plain text inside `\small{}`.
- Keep it to 2–4 sentences.

---

### Education

```latex
\newcommand{\educationSection}{%
  \section{Education}
  \resumeSubHeadingListStart
    \resumeSubheading
      {University Name}{City, State}
      {Degree Title; GPA: X.XX}{Month Year -- Month Year}
  \resumeSubHeadingListEnd
}
```

- Each degree = one `\resumeSubheading`.
- Most recent degree goes first.

---

### Experience

```latex
\newcommand{\experienceSection}{%
  \section{Experience}
  \resumeSubHeadingListStart
    \resumeSubheading
      {Company Name}{City, State}
      {Job Title}{Month Year -- Present}
      \resumeItemListStart
        \resumeItem{Project or Feature Name}
          {What you built, improved, or owned.}
      \resumeItemListEnd
  \resumeSubHeadingListEnd
}
```

- Each employer = one `\resumeSubheading`.
- Most recent job goes first.
- Each responsibility/project inside a job = one `\resumeItem`.

---

### Projects

```latex
\newcommand{\projectsSection}{%
  \section{Projects}
  \resumeSubHeadingListStart
    \resumeSubItem{Project Name}
      {Short description of what it is and what tech it uses.}
  \resumeSubHeadingListEnd
}
```

- Each project = one `\resumeSubItem`.
- No nested item lists needed here.

---

### Skills

```latex
\newcommand{\skillsSection}{%
  \section{Skills}
  \resumeSubHeadingListStart
    \resumeSubItem{Languages}{Python, JavaScript, SQL}
    \resumeSubItem{Technologies}{AWS, Docker, React}
  \resumeSubHeadingListEnd
}
```

- Each category = one `\resumeSubItem`.
- Values are comma-separated plain text — no bullet points inside.

---

## Rules to Always Follow

1. **Never read or edit `data-contact.tex`** — this file is strictly for the user to manage manually. AI should not open, read, reference, or suggest changes to it under any circumstance.
2. **Never edit `main.tex`** — it controls formatting. Only touch it if the user explicitly asks.
3. **Only edit `data-resume.tex`** for all resume content updates.
4. **Do not create new commands** — only use the helper commands listed above.
5. **Preserve all `\newcommand` wrappers** — do not rename or delete them.
6. **Keep the `%` comment headers** (e.g., `% ========================`) — they help humans read the file.
7. **Most recent entries go first** — for both Experience and Education.
8. **Do not add extra `\vspace` or formatting tweaks** — layout is already handled by `main.tex`.

---

## Quick Reference: Common Tasks

| Task                            | What to do                                                                                    |
| ------------------------------- | --------------------------------------------------------------------------------------------- |
| Add a new job                   | Add a `\resumeSubheading` + `\resumeItemListStart` block inside `\experienceSection`          |
| Add a bullet to an existing job | Add a `\resumeItem` inside that job's `\resumeItemListStart` block                            |
| Add a new skill category        | Add a `\resumeSubItem` inside `\skillsSection`                                                |
| Add a project                   | Add a `\resumeSubItem` inside `\projectsSection`                                              |
| Add a degree                    | Add a `\resumeSubheading` inside `\educationSection`                                          |
| Update summary                  | Edit the text inside `\small{}` in `\summarySection`                                          |
| Reorder sections                | Reorder the macro calls at the bottom of the file                                             |
| Remove a section entirely       | Remove its macro call from the bottom list (keep the `\newcommand` block itself unless asked) |
