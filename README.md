# Joseph L. Austerweil — Curriculum Vitae

### 📄 [**Download the current CV (PDF)**](JoeAusterweilCV.pdf)

Also served at **<https://josephausterweil.github.io/academic-cv/>**

*Last updated: September 2026*

---

Professor and Academic Director (co-founding faculty member),
School of Design & Science, Chiba Institute of Technology.

- Lab: [Computational Mind Laboratory](https://cml.chibatech.dev)
- Courses: [APS-I](https://aps-i.chibatech.dev) · [Human and Machine Learning](https://hml.chibatech.dev)
- Open textbook: [A Narrative Introduction to Probability](https://josephausterweil.github.io/probintro/)

## Repository contents

| File | Purpose |
| --- | --- |
| `JoeAusterweilCV.pdf` | Built CV — the file most people want |
| `JoeAusterweilCV.tex` | Main LaTeX source |
| `cv.sty` | Styles, and the biblatex configuration |
| `jlapubs.bib` | Publication database |
| `2025_papers_presentations.md` | Summary of 2025 papers and talks |
| `researchmap_*.csv` | Exports formatted for [researchmap](https://researchmap.jp/) |

## Building

The bibliography uses **biblatex with the biber backend**, so a plain
`pdflatex` run is not enough:

```sh
pdflatex JoeAusterweilCV
biber    JoeAusterweilCV
pdflatex JoeAusterweilCV
pdflatex JoeAusterweilCV
```

Two things worth knowing before editing:

- **Line 1 of `JoeAusterweilCV.tex` pins the LaTeX kernel** to `2020-02-02`
  via `latexrelease`. The `tabu` package's `X` columns break on current
  kernels, which silently drops the right-hand date column out of every
  `longtabu` table. Don't remove that line unless you also migrate off `tabu`.
- **Publications sort themselves.** `cv.sty` sets `sorting=ydnt`, so each
  bibliography category orders newest-first regardless of the order keys are
  listed in `\addtocategory`. Entries whose year is text rather than a number
  ("in press", "in revision") need an explicit `sortyear` in `jlapubs.bib` to
  float to the top — the convention is documented in `cv.sty`.
