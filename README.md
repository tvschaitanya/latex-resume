# 📄 Modular LaTeX Resume

A modular LaTeX-based resume system designed for simplicity, flexibility, and AI-assisted editing.  
It separates content, contact information, and the core template to make updates fast and maintainable.

---

## 📁 Project Structure

```
.
├── main.tex
├── data-resume.tex
├── data-contact.tex
└── AI-Guide.md
```

---

## 🧩 Components

### `main.tex`
- Core LaTeX template used to compile the resume
- Acts as the layout/engine of the system
- ⚠️ Should NOT be edited in normal usage
- Only modify if there are structural or compilation issues

---

### `data-resume.tex`
- Contains all resume content:
  - Experience
  - Education
  - Skills
  - Projects
- Fully modular design:
  - Sections can be reordered freely
  - Sections can be hidden using LaTeX comments

---

### `data-contact.tex`
- Stores personal contact information separately
- Can be enabled/disabled easily
- Useful for:
  - Privacy control
  - Multiple resume versions (e.g., public vs private)

---

### `AI-Guide.md`
- Designed for AI tools (ChatGPT, Claude, etc.)
- Used to generate or improve resume content
- Example prompts:
  - “Improve my resume for ATS optimization”
  - “Rewrite my experience section professionally”
  - “Add a new job entry”

- AI returns a fully formatted `data-resume.tex` ready to copy-paste

---

## ✨ Key Features

- 🧱 Fully modular LaTeX architecture
- 🔒 Separation of concerns:
  - Contact info (`data-contact.tex`)
  - Content (`data-resume.tex`)
  - Template (`main.tex`)
- ✏️ Easy editing:
  - Reorder sections freely
  - Enable/disable sections with comments
- 🔐 Privacy-friendly design
- 🤖 AI-assisted resume generation workflow
- 🧼 Minimal maintenance required for `main.tex`
- 🔀 Version-control friendly (reduced merge conflicts)

---

## 🚀 Workflow

1. Edit or generate content in `data-resume.tex`
2. Update `data-contact.tex` if needed
3. Compile using `main.tex`
4. Optionally use `AI-Guide.md` to improve or regenerate content with AI

---

## 🧠 AI Integration

This project is optimized for AI-assisted resume editing.

How to use:
1. Paste `AI-Guide.md` into an AI tool
2. Ask for updates or improvements
3. Copy the generated `data-resume.tex` back into the project

---

## 📌 Notes

- You generally do not need to modify `main.tex`
- Prefer commenting out sections instead of deleting them
- Keep content modular for easier AI and manual updates
