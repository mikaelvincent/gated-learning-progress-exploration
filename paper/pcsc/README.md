# PCSC 2026 paper

LaTeX sources of the paper "Gated Learning-Progress Exploration" (Philippine Computing Science
Congress, PCSC 2026). The compiled paper is `GLPE-PCSC2026-paper.pdf` in the repository root.

## Contents

- `sections/`: the paper text (`00_abstract.tex` to `05_conclusion.tex`).
- `content.tex`, `content_body.tex`: shared bodies that input the sections. `content_body.tex` is the
  body without the abstract (used by `pcsc.tex` and `icml.tex`, which input the abstract themselves);
  `content.tex` also inputs the abstract (used by `arxiv.tex`, `iclr.tex` and `neurips.tex`).
- `figures/`, `tables/`: figures (PNG plus their `.tex` wrappers) and tables.
- `references/references.bib`: the bibliography.
- `targets/`: one wrapper per venue format: `pcsc.tex` (ACM `acmart`, the PCSC paper), `arxiv.tex`,
  `iclr.tex`, `icml.tex` and `neurips.tex`.
- `templates/`: venue style files, one folder per target except `arxiv`. These are third-party and keep their
  own licences (see [`../LICENSE`](../LICENSE), section 3).
- `scripts/build_paper.py`: the build script.

## Build

Requires Python 3, a TeX distribution and `latexmk` on `PATH`. From the repository root:

```bash
python paper/pcsc/scripts/build_paper.py pcsc          # the PCSC 2026 paper
python paper/pcsc/scripts/build_paper.py --all         # every target
```

Options: `--engine {pdflatex,xelatex,lualatex}` (default `pdflatex`), `--latexmk PATH`, `--clean`
(remove the target's build folder first) and `--no-stage` (skip the staged sources). The `pcsc`
target needs `templates/pcsc/acmart.cls`; `neurips`, `icml` and `iclr` need their style files in
`templates/`; `arxiv` needs none. The script runs `latexmk` on `targets/<target>.tex` from
`paper/pcsc/`.

Output goes to `paper/pcsc/build/<target>/<target>.pdf`, with self-contained sources staged in
`paper/pcsc/build/<target>/latex/`. The build does not write to the repository root, so the root
`GLPE-PCSC2026-paper.pdf` is the final compiled copy and is not overwritten by a rebuild.

## License

All rights reserved by the authors, except the third-party templates; see [`../LICENSE`](../LICENSE).
