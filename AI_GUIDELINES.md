# 🤖 AI ASSISTANT GUIDELINES & PROMPTING RULES

This document specifies the strict architectural and formatting rules that AI assistants (ChatGPT, Claude, Gemini, Cursor, Copilot, etc.) **MUST** adhere to when generating, modifying, or refactoring code and content in this LaTeX project.

---

## 1. 📌 Core Architectural Principles

1. **Keep `main.tex` strictly structural:**
   - `main.tex` serves only as a driver combining modules via `\input{...}`.
   - All chapter contents must reside exclusively within the `chapters/` directory.
2. **Do NOT redeclare preambles in subfiles:**
   - Subfiles in `chapters/`, `frontmatter/`, and `appendices/` **must never** contain `\documentclass`, `\usepackage`, `\begin{document}`, or `\end{document}`.
3. **Manage project metadata via macros:**
   - Update project title, authors, instructor, course code, etc., strictly by editing the predefined macros in `preamble.tex` (`\ProjectTitle`, `\StudentName`, `\InstructorName`...). Never hardcode them directly into `frontmatter/titlepage.tex`.

---

## 2. ✍️ Typography & Text Formatting

1. **Paragraphs and Spacing:**
   - The project uses zero indentation (`\parindent = 0cm`) and 6pt paragraph separation (`\parskip = 6pt`).
   - **Do not** insert consecutive line breaks (`\\ \\`) or manual `\vspace` commands between ordinary body paragraphs. Use a single blank line in `.tex` source code.
2. **Heading Hierarchy:**
   - Level 1 (Chapter): `\chapter{CHAPTER TITLE}` (Automatic uppercase, centered, 14pt bold).
   - Level 2 (Section): `\section{Section Title}` (13pt bold, left-aligned).
   - Level 3 (Subsection): `\subsection{Subsection Title}` (13pt bold italic).
   - Level 4 (Subsubsection): `\subsubsection{Subsubsection Title}` (13pt bold, labeled a, b, c...).
   - **Do not** simulate headings using manual formatting like `\textbf{\large ...}`.

---

## 3. 📊 Table Specifications

All newly generated tables must follow this pattern:

```latex
\begin{table}[H]
    \caption{Clear and concise table caption}
    \label{tab:unique_table_label}
    \centering
    \begin{tabular}{|l|p{6cm}|c|}
        \hline
        \textbf{Col 1} & \textbf{Col 2 (Long descriptive text)} & \textbf{Col 3} \\ \hline
        Entry 1 & Multiline wrapped content goes here & 100 \\ \hline
    \end{tabular}
    \source{State source or "Author's compilation"}
\end{table}
```

* **Rules:**
  - Table captions (`\caption`) **must be placed on top** of the table.
  - Always use `[H]` from the `float` package.
  - Always append `\source{...}` immediately after `\end{tabular}`.
  - Reference tables in prose using: `Table~\ref{tab:unique_table_label}`.

---

## 4. 🖼️ Figure Specifications

```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{figure_filename.png}
    \caption{Descriptive figure caption}
    \label{fig:unique_fig_label}
    \source{State source or "Author's illustration"}
\end{figure}
```

* **Rules:**
  - Place all image files in `figures/`.
  - In `\includegraphics`, **omit** the `figures/` directory prefix because `\graphicspath{{figures/}}` is preconfigured.
  - Figure captions (`\caption`) **must be placed below** the image.
  - Always append `\source{...}` immediately after `\caption{...}`.
  - Reference figures in prose using: `Figure~\ref{fig:unique_fig_label}`.

---

## 5. 🧮 Mathematical Formulations

- Inline math: `$E = mc^2$`.
- Numbered single-line equations:
  ```latex
  \begin{equation}
      y = f(x) = ax^2 + bx + c
      \label{eq:quadratic}
  \end{equation}
  ```
- Multiline aligned equations: Use `aligned` inside `equation`:
  ```latex
  \begin{equation}
  \begin{aligned}
      A &= B + C \\
        &= D + E + F
  \end{aligned}
  \label{eq:derivation}
  \end{equation}
  ```
- Reference equations in prose using: `Equation~\eqref{eq:quadratic}`.

---

## 6. 💻 Code Listings

For code listings, use the `listings` package environment:

```latex
\begin{lstlisting}[language=Python, caption={Sample algorithm implementation}, label={lst:sample_code}]
def hello_world():
    print("UTH LaTeX Template")
\end{lstlisting}
```
- Reference code listings in prose using: `Listing~\ref{lst:sample_code}`.

---

## 7. 📚 Bibliographic References

1. All cited works must be declared in BibTeX format in `refs.bib`.
2. Cite within text using `\cite{bib_key}` (renders IEEE style `[1]`, `[2]`).
3. **Never** hardcode citations or manual `\begin{thebibliography}` blocks inside chapters.
