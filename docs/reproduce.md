# Reproduce

This is a starter reproducibility guide. I’ll make the commands and dataset IDs fully exact once the thesis pipeline is locked.

!!! note "Goal"
    You should be able to (1) set up the environment reliably, (2) run a precomputed evaluation (coming soon), and (3) later reproduce training + evaluation from tracked configs.

---

## 1) Clone the code repo

'''bash
git clone git@github.com:OAE-PINN-Emulator/OAE-PINN-Emulator.git
cd OAE-PINN-Emulator
'''

---

## 2) Create the environment (uv)

If the repo contains `pyproject.toml` + `uv.lock`:

'''bash
uv sync
'''

Run any command like:

'''bash
uv run python --version
'''

!!! tip "Recommended workflow"
    Prefer `uv run ...` over manually activating a virtualenv. It keeps runs consistent and reproducible.

---

## 3) Data + outputs layout

Recommended (kept out of git):

'''bash
# from the repo root
mkdir -p data outputs
'''

- `data/` → NetCDF datasets (Oceananigans output or downloaded sample)
- `outputs/` → checkpoints, predictions, plots, logs

!!! warning "Do not commit large artifacts"
    Keep NetCDFs, checkpoints, and generated outputs in `data/`/`outputs/` (gitignored).

---

## 4) Precomputed demo evaluation (placeholder)

This will become the “one command” path.

'''bash
# placeholder (will be made exact)
uv run python -m oae_pinn.eval --config configs/demo.yaml
'''

Planned outputs:
- a figure/GIF saved under `outputs/`
- a metrics JSON/CSV

---

## 5) Train + evaluate from configs (placeholder)

'''bash
# TRAIN (placeholder)
uv run python -m oae_pinn.train --config configs/baseline.yaml

# EVAL (placeholder)
uv run python -m oae_pinn.eval --config configs/baseline.yaml
'''

!!! note "To be finalized"
    These module names and config paths will be updated to match the final repo structure and CLI.

---
