# LaTeX Resume Template

## What Is This?

A modular LaTeX resume template that separates your personal information and content into different files. You edit simple text files, and it generates a professional PDF resume.

## Why Use This?

- **Keep things organized**: Contact info and resume content are in separate files
- **Easy updates**: Change your content without touching the formatting
- **ATS-friendly**: Clean, single-column layout that applicant tracking systems can read
- **Reusable**: Update once, compile anytime you need a new PDF

## How to Use It

### Step 1: Upload to Overleaf

1. Go to [Overleaf.com](https://www.overleaf.com) and sign up (it's free)
2. Click "New Project" → "Upload Project"
3. Upload all the files from this template
4. Overleaf will open your project

### Step 2: Edit Your Contact Information

1. Click on `data-contact.tex` in the left sidebar
2. Replace the example information with yours:
   - Name, phone, email
   - LinkedIn, GitHub, portfolio
3. Leave any field blank `{}` if you don't want to show it

### Step 3: Edit Your Resume Content

1. Click on `data-resume.tex` in the left sidebar
2. Replace the example content with your own:
   - Summary
   - Education
   - Experience
   - Projects
   - Skills
   - Certifications
3. Follow the same format as the examples

### Step 4: Generate Your PDF

Click the "Recompile" button in Overleaf. Your resume PDF will appear on the right side. Download it when you're happy with it.

## How to Use the AI Guide

The `AI_Guide.md` file teaches AI how to help you write better resume content. It includes:

- **Writing frameworks**: How to structure strong bullet points with action verbs and results
- **ATS optimization**: Which keywords to include and how to use them naturally
- **Job tailoring**: How to customize your resume for specific job descriptions
- **Real examples**: Before/after comparisons showing weak vs strong bullets

### Example Prompt

Copy and paste this into your AI chat (like ChatGPT or Claude):

```
I'm updating my resume using a LaTeX template. Here's the job description I'm applying for:

[Paste the job description here]

Here's my current experience section:

[Paste your experience section from data-resume.tex]

Please help me:
1. Rewrite my bullets to match the job description
2. Add quantifiable results where possible
3. Include relevant keywords from the job posting
4. Make sure each bullet follows the format: Action Verb + What I Did + Result

Give me the complete LaTeX code I can paste back into data-resume.tex.
```

**Pro tip**: If you want even better results, upload the `AI_Guide.md` file to your AI chat along with your prompt. This gives the AI detailed instructions on resume writing best practices, resulting in stronger, more professional content that's tailored to your target job.

## That's It!

Edit the two data files, recompile in Overleaf, and download your resume. Use the AI guide to make your content stronger.
