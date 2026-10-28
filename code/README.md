# intrinsic-rl: code for Gated Learning-Progress Exploration (GLPE)

The Python package `irl` (installed as `intrinsic-rl`) with the PPO trainer, the
intrinsic-reward methods, YAML experiment configs per environment and the `intrinsic-rl`
command line. For the project overview, paper and thesis, see the [root README](../README.md).

## Layout

- `irl/`: the Python package.
- `configs/`: YAML experiment configs, one folder per environment (`ant_v5`,
  `bipedalwalker_v3`, `halfcheetah_v5`, `humanoid_v5`, `mountaincar_v0`).
- `results_suite/`: the stored suite results (CSV summaries, `eval_meta.json`, `plots/`).
- `results/benchmarks/`: stored microbenchmark output.
- `tests/`: the pytest suite.
- `utilities/config_splitter/`: scripts that split the configs into per-VM sets and verify the result.

## Setup

Requires Python 3.10 or 3.11. Run the commands from this directory (`code/`), because the
suite commands read `configs/` and write `runs_suite/` and `results_suite/` relative to the
current directory.

```bash
pip install -e .                 # core dependencies (PyTorch, Gymnasium, ...)
pip install -e ".[box2d]"        # optional: BipedalWalker
pip install -e ".[mujoco]"       # optional: Ant, HalfCheetah, Humanoid
pip install -e ".[dev]"          # optional: pytest
```

## Usage

```bash
intrinsic-rl --help
intrinsic-rl suite train         # train every config under configs/ (all configured seeds)
intrinsic-rl suite eval          # evaluate the trained runs
intrinsic-rl suite plots         # make the plots
intrinsic-rl suite videos        # make the videos
intrinsic-rl suite validate      # validate the suite outputs
intrinsic-rl suite full          # train, eval, plots, videos and validate in one go
intrinsic-rl bench               # microbenchmarks
```

The commands take no options; paths and defaults are fixed in `irl/paper_defaults.py`.

## Tests

```bash
pytest
```

## License

MIT, see [`../LICENSE`](../LICENSE).
