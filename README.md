# Gated Learning-Progress Exploration (GLPE)

Research code, paper and thesis for **Gated Learning-Progress Exploration (GLPE)**, an
intrinsic-reward family for reinforcement learning. GLPE prioritizes transitions that change
a learned feature representation and that occur in regions where a forward dynamics model is
still improving. It estimates region-local learning progress from the gap between short- and
long-horizon moving averages of prediction error, and an optional gate suppresses intrinsic
reward in regions where prediction error stays high but learning progress is low. It is
evaluated with a PPO backbone against common intrinsic-reward baselines on five Gymnasium
control benchmarks (abstract of the paper, `paper/pcsc/sections/00_abstract.tex`).

## Repository layout

- [`code/`](code/README.md): the Python package `irl` (installed as `intrinsic-rl`) with the PPO trainer, the
  intrinsic-reward methods, YAML experiment configs per environment (`code/configs/`), the
  stored suite results (`code/results_suite/`) and tests.
- [`paper/pcsc/`](paper/pcsc/README.md): LaTeX sources of the PCSC 2026 paper "Gated Learning-Progress Exploration".
- [`paper/thesis/`](paper/thesis/README.md): LaTeX sources of the thesis.
- [`GLPE-PCSC2026-paper.pdf`](GLPE-PCSC2026-paper.pdf), [`GLPE-thesis.pdf`](GLPE-thesis.pdf): the compiled paper and thesis.

## Getting started

Setup and usage of the code (requirements, installation, the `intrinsic-rl` commands and the
tests) are in [`code/README.md`](code/README.md).

## License

- `code/` is under the MIT License (see [`LICENSE`](LICENSE)).
- `paper/`, the thesis, `GLPE-PCSC2026-paper.pdf` and `GLPE-thesis.pdf` are copyright 2025-2026
  the authors, all rights reserved (see [`paper/LICENSE`](paper/LICENSE)).
- Third-party material (reviews, certificates, forms, web capture, logos, CVs) stays with its
  owners, and `paper/pcsc/templates/` keeps its own terms (see [`paper/LICENSE`](paper/LICENSE)).

## How to cite

See [`CITATION.cff`](CITATION.cff) (GitHub: "Cite this repository"). The paper is: Mikael Vincent Tumampos,
Ervin Joshua Guirnela and Christine Peña, "Gated Learning-Progress Exploration",
Philippine Computing Science Congress (PCSC 2026), Davao City, Philippines
([proceedings](https://pcsc2026.uic.edu.ph/papers)).

The thesis is: Mikael Vincent Tumampos and Ervin Joshua Guirnela, "Gated Learning-Progress
Exploration", Bachelor's thesis (BS Computer Science), University of San Carlos, May 2026.
