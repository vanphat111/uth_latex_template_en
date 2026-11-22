# UTH LaTeX Template (English Version) 🎓

A modular, publication-ready LaTeX report template designed for students and researchers at **Ho Chi Minh City University of Transport (UTH)**.

Fully optimized for **Overleaf** and local compilation (TeX Live / VS Code / Makefile).

---

## 📁 Project Directory Structure

```text
uth_latex_template_en/
├── main.tex                    # Main driver file (clean structural \input only)
├── preamble.tex                # Packages, 13pt Times typography, project metadata
├── refs.bib                    # BibTeX bibliographic database
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

## 💡 Best Practices & Conventions

* **Inserting Figures:** Place images in `figures/` (e.g., `figures/my_chart.png`). Call `\includegraphics[width=...]{my_chart.png}` directly (the search path `figures/` is preconfigured).
* **Source Attribution:** Use `\source{Source Name}` right after `\caption{...}` for figures and tables.
* **Citations:** Add entries to `refs.bib` and cite them in text using `\cite{key}` (IEEE format `[1]`, `[2]`).
* **Source Code Listings:** Use the `\begin{lstlisting}[language=Python] ... \end{lstlisting}` environment.

---

## 📄 License
Released under the [MIT License](LICENSE).
