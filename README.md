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

- `code/`: the Python package `irl` (installed as `intrinsic-rl`) with the PPO trainer, the
  intrinsic-reward methods, YAML experiment configs per environment (`code/configs/`), the
  stored suite results (`code/results_suite/`) and tests.
- `paper/pcsc/`: LaTeX sources of the PCSC 2026 paper "Gated Learning-Progress Exploration".
- `paper/thesis/`: LaTeX sources of the thesis.
- `pcsc.pdf`, `thesis.pdf`: the compiled paper and thesis.

## Quick start

Requires Python 3.10 or 3.11. Run the commands from `code/`, because the suite commands read
`configs/` and write `runs_suite/` and `results_suite/` relative to the current directory.

```bash
cd code
pip install -e .                 # core dependencies (PyTorch, Gymnasium, ...)
pip install -e ".[box2d]"        # optional: BipedalWalker
pip install -e ".[mujoco]"       # optional: Ant, HalfCheetah, Humanoid
pip install -e ".[dev]"          # optional: pytest

intrinsic-rl --help
intrinsic-rl suite train         # train every config under configs/ (all seeds)
intrinsic-rl suite eval          # evaluate the trained runs
intrinsic-rl suite plots         # make the plots
intrinsic-rl suite full          # train, eval, plots, videos and validate in one go
intrinsic-rl bench               # microbenchmarks
pytest                           # tests
```

## License

- `code/` is under the MIT License (see `LICENSE`).
- `paper/`, the thesis, `pcsc.pdf` and `thesis.pdf` are copyright 2025-2026 the authors, all
  rights reserved (see `paper/LICENSE`).
- Third-party material (reviews, certificates, forms, web capture, logos, CVs) stays with its
  owners, and `paper/pcsc/templates/` keeps its own terms (see `paper/LICENSE`).

## How to cite

See `CITATION.cff` (GitHub: "Cite this repository"). The paper is: Mikael Vincent Tumampos,
Ervin Joshua Guirnela and Christine Peña, "Gated Learning-Progress Exploration",
Philippine Computing Science Congress (PCSC 2026), Davao City, Philippines.
