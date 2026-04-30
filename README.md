# Modular LaTeX Resume

A modular LaTeX-based resume system designed for simplicity, flexibility, and AI-assisted editing.  
It separates content, contact information, and the core template to make updates fast and maintainable.

This project is designed to be used directly in **Overleaf** for PDF compilation and export.

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

## 🚀 How to Use (Overleaf)

This project is designed to be compiled using **Overleaf**.

### 1. Upload to Overleaf
- Go to https://www.overleaf.com
- Create a new project → “Upload Project”
- Upload all files:
  - `main.tex`
  - `data-resume.tex`
  - `data-contact.tex`
  - `AI-Guide.md`

---

### 2. Compile the Resume
- Open `main.tex` in Overleaf
- Ensure it is set as the **main document**
- Overleaf will automatically compile the PDF

---

### 3. Export PDF
- Click **“Download PDF”** in Overleaf
- Or use **Menu → Download → PDF**

---

## 🧠 AI Integration

This project is optimized for AI-assisted resume editing.

### How to use:
1. Paste `AI-Guide.md` into an AI tool (ChatGPT, Claude, etc.)
2. Ask for updates or improvements
3. Copy the generated `data-resume.tex` back into the project
4. Recompile in Overleaf

---

## 📌 Notes

- You generally do not need to modify `main.tex`
- Prefer commenting out sections instead of deleting them
- Keep content modular for easier AI and manual updates
- Overleaf handles all compilation — no local LaTeX setup needed
