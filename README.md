# UTH LaTeX Template (English Version) 🎓

A modular, publication-ready LaTeX report template designed for students and researchers at **Ho Chi Minh City University of Transport (UTH)**.

Fully optimized for **Overleaf**, local compilation (TeX Live / VS Code / Makefile), and **AI Assistant workflows** (Cursor, ChatGPT, Claude, Gemini...).

---

## 📁 Project Directory Structure

```text
uth_latex_template_en/
├── main.tex                    # Main driver file (clean structural \input only)
├── preamble.tex                # Packages, 13pt Times typography, project metadata
├── refs.bib                    # BibTeX bibliographic database
├── AI_GUIDELINES.md            # Mandatory rules & prompts for AI Assistants
├── README.md                   # Project documentation & structure guide
├── Makefile                    # Automated build scripts for Linux/macOS
├── .gitignore                  # Ignore auxiliary LaTeX build artifacts
│
├── frontmatter/                # Preliminary pages (Roman numerals i, ii, iii...)
│   ├── titlepage.tex           # Formal double-border TikZ cover page
│   ├── declaration.tex         # Declaration of Authorship
│   ├── acknowledgments.tex     # Acknowledgments
│   └── abbreviations.tex       # List of Abbreviations table
│
├── chapters/                   # Core document body (Arabic numbering 1, 2, 3...)
│   ├── 01_introduction.tex     # Chapter 1: Introduction, background, objectives
│   ├── 02_theoretical_background.tex  # Chapter 2: Theoretical foundations & math
│   ├── 03_methodology.tex      # Chapter 3: System architecture & methodology
│   ├── 04_implementation_results.tex  # Chapter 4: Implementation & evaluation
│   └── 05_conclusion.tex       # Chapter 5: Conclusion & future work
│
├── appendices/                 # Appendices (A, B, C...)
│   └── appendix_a.tex          # Appendix A: Code repository & supplementary data
│
├── figures/                    # Graphics & diagrams directory
│   └── uth_logo.png            # Official UTH logo
│
├── tables/                     # Complex standalone table files (optional)
└── code/                       # Source code scripts (optional)
```

---

## 🤖 AI Assistant Guidelines (Cursor, ChatGPT, Claude, Copilot...)

When using AI coding assistants to write or edit chapters, feed [AI_GUIDELINES.md](AI_GUIDELINES.md) as project context or system prompt:

### Core Rules for AI:
1. **Modular Scope:** Never write content directly in `main.tex`. All chapters belong to `chapters/`. Subfiles must never redeclare `\documentclass` or `\begin{document}`.
2. **Metadata via Macros:** Change author, title, instructor, etc., in `preamble.tex` via macros—never hardcode strings inside `frontmatter/titlepage.tex`.
3. **Table Standards:**
   - Always use `[H]` placement.
   - `\caption{...}` must be placed **above** the table.
   - Must append `\source{...}` right after `\end{tabular}`.
4. **Figure Standards:**
   - Always use `[H]` placement. Store images in `figures/` (do not prefix `figures/` in `\includegraphics`).
   - `\caption{...}` must be placed **below** the image.
   - Must append `\source{...}` right after `\caption{...}`.
5. **Citations:** Add entries to `refs.bib` and cite with `\cite{key}` (IEEE format `[1]`, `[2]`). Never manually hardcode brackets.

👉 *See full guidelines and code snippets in [AI_GUIDELINES.md](AI_GUIDELINES.md).*

---

## 🚀 Quick Start Guide

### 1. Using with Overleaf (Recommended)
1. Download this repository as a `.zip` archive (via **Code** $\rightarrow$ **Download ZIP** on GitHub).
2. Log into [Overleaf](https://www.overleaf.com/).
3. Click **New Project** $\rightarrow$ **Upload Project** and drag-and-drop the `.zip` file.
4. Set the default compiler to **pdfLaTeX** and press **Recompile**.

### 2. Local Compilation (Linux / macOS / Windows)
Prerequisite: A standard TeX Live installation.

```bash
# Build main.pdf with bibliography
make

# Clean temporary auxiliary files (*.aux, *.log, *.toc...)
make clean

# Watch mode for automatic re-compilation on file save (requires latexmk)
make watch
```

---

## ⚙️ Customization & Metadata

All report metadata is centralized at the bottom of `preamble.tex`. Simply edit the following macros:

```latex
\newcommand{\UnivName}{HO CHI MINH CITY UNIVERSITY OF TRANSPORT}
\newcommand{\InstituteName}{FACULTY / INSTITUTE NAME}
\newcommand{\ReportType}{PROJECT REPORT}
\newcommand{\ProjectTitle}{YOUR PROJECT TITLE GOES HERE IN UPPERCASE}
\newcommand{\CourseName}{Course Subject Name}
\newcommand{\ClassCode}{CLASS-123456}
\newcommand{\InstructorName}{Dr. John Doe}
\newcommand{\StudentName}{Student Full Name}
\newcommand{\StudentID}{1234567890}
\newcommand{\LocationDate}{Ho Chi Minh City, Month Year}
```
*The cover page, declaration, and acknowledgments will automatically sync with these variables!*

---

## 📄 License
Released under the [MIT License](LICENSE).
