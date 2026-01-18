# LaTeX Project Template

A modular LaTeX template for academic papers, descended from the legendary `alptex`.

## Quick Start

1. Click **"Use this template"** on GitHub to create a new repository
2. Clone your new repo
3. Edit `main.tex` to update title, authors, and affiliations
4. Add your content to `sections/`
5. Build with `latexmk -pdf main.tex`

## Quick Start in Overleaf

[![Open in Overleaf](https://img.shields.io/badge/Open%20in-Overleaf-47A141?logo=overleaf&logoColor=white)](https://www.overleaf.com/docs?snip_uri=https://github.com/schein-lab/alptex/archive/refs/heads/main.zip)

## Structure

```
├── main.tex                 # Main document (title, authors, structure)
├── preamble.tex             # Package imports and configuration
├── preamble/
│   ├── preamble_math.tex    # Math packages, theorem environments
│   ├── definitions_basic.tex # Custom notation and macros
│   ├── commenting.tex       # Draft mode: colored TODO/PROBLEM comments
│   ├── nocommenting.tex     # Production mode: errors on leftover comments
│   └── minimalist_biblatex.tex # Alternative biblatex configuration
├── sections/
│   ├── 0_abstract.tex
│   ├── 1_intro.tex
│   └── 2_background.tex
├── references.bib           # Bibliography
├── .latexmkrc               # Build configuration
└── .gitignore
```

## Features

### Fonts
Three font options (uncomment in `preamble.tex`):
- **Option 2 (default):** Bitstream Charter + MathDesign + PTSans
- Option 1: New Century Schoolbook + Fourier Math + PTSans
- Option 3: Times (Termes) + MTPro2 Math + PTSans

### Draft Comments
Use these macros during drafting:
- `\PROBLEM{text}` — orange box for issues
- `\fPROBLEM{text}` — inline orange highlight (footnote-style)
- `\TBD{text}` — blue box for todos
- `\fTBD{text}` — inline blue highlight
- `\LATER{text}` — gray box for deferred items
- `\NA{text}` — renders text normally (for resolved comments)

For production, swap `commenting.tex` for `nocommenting.tex` in `preamble.tex` — any leftover comments will cause build errors.

### Math Notation
Common macros in `definitions_basic.tex` e.g.,:
- `\E{subscript}{content}` — expectation
- `\defeq` — definition equals
- `\iidsim`, `\indsim` — iid/independent sim
- `\argmin`, `\argmax` — operators

### Theorem Environments
Defined in `preamble_math.tex`:
- `theorem`, `lemma`, `proposition`, `cor`, `claim`, `conj`
- `defn`, `assumption`, `example`, `remark`

## Building
```bash
# Full build with bibliography
latexmk -pdf main.tex

# Clean auxiliary files
latexmk -c

# Continuous compilation (watches for changes)
latexmk -pdf -pvc main.tex
```

## Requirements
TeX Live or MacTeX with these packages:
- `mathdesign`, `PTSans` (fonts)
- `authblk`, `natbib`, `cleveref`, `hyperref`
- `thmtools`, `mathtools`, `algorithm2e`

