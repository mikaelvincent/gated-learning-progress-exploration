# Thesis

LaTeX sources of the thesis on Gated Learning-Progress Exploration. The compiled thesis is
`GLPE-thesis.pdf` in the repository root.

## Contents

- `main.tex`: the entry point. It inputs the front matter, the chapters, the bibliography, the
  appendices and the curricula vitae. `latex_utilities.tex` holds shared definitions.
- `sections/`: front matter (title page, approval, declaration, acknowledgements, abstract),
  `97_references.bib`, `98_appendices.tex` and `99_curricula_vitae.tex`.
- `chapters/`: the six chapters, from `01_introduction` to `06_conclusion_and_recommendations`.
- `sections/images/`: page images of supporting documents, one folder each for the approval and
  declaration forms, the reviews, the certificate, the proof of publication, the PCSC paper pages
  and a co-author's curriculum vitae.
- `scripts/build_thesis.py`: the build script. `scripts/pdf_to_page_images.py` converts a PDF to page
  images (`python paper/thesis/scripts/pdf_to_page_images.py path/to/file.pdf`).

Some pages are third-party documents included as images (approval and declaration forms,
reviews, certificate, proof of publication, a co-author's curriculum vitae). They stay with their
owners; see [`../LICENSE`](../LICENSE), section 2.

## Build

Requires Python 3, a TeX distribution and `latexmk` on `PATH`. `main.tex` uses `biblatex` with the
`biber` backend. From the repository root:

```bash
python paper/thesis/scripts/build_thesis.py
```

Options: `--engine {pdflatex,xelatex,lualatex}` (default `pdflatex`), `--latexmk PATH`, `--clean`
(remove the build folder first) and `--no-stage` (skip the staged sources). The script runs
`latexmk` on `main.tex` from `paper/thesis/`.

Output goes to `paper/thesis/build/thesis.pdf` (LaTeX intermediates in `paper/thesis/build/out/`,
staged sources in `paper/thesis/build/latex/`). The build does not write to the repository root,
so the root `GLPE-thesis.pdf` is the final compiled copy and is not overwritten by a rebuild.

## License

All rights reserved by the authors, except the third-party material above; see
[`../LICENSE`](../LICENSE).
