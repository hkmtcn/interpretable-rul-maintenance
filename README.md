# interpretable-rul-maintenance
RUL, Prognostics, C-MAPSS, Maintenance Scheduling, Aircraft Engines

# Interpretable Ensemble Remaining Useful Life Prediction Enables Dynamic Maintenance Scheduling for Aircraft Engines

This repository hosts code, notebooks, and produced artifacts for the paper:

**Interpretable Ensemble Remaining Useful Life Prediction Enables Dynamic Maintenance Scheduling for Aircraft Engines** — *Hikmetcan Özcan*.

The project provides an interpretable **Remaining Useful Life (RUL)** prediction pipeline and a **dynamic maintenance scheduling** policy. We train tree-based learners (e.g., LightGBM, CatBoost, Gradient Boosting / XGBoost variants) and combine them via simple ensembles. Maintenance is triggered when the predicted RUL falls below a tunable threshold **τ** (default: 15 cycles), enabling cost–risk trade-offs for scheduling.

---

## Repository contents

```
.
├─ README.md
├─ LICENSE                # Code under MIT; figures/data artifacts under CC BY 4.0
├─ notebooks/             # Reproducible analysis notebooks (Ablations, models)
├─ results/				  # All generated output files (per C-MAPSS subset)          
```

> **Note:** Raw datasets are **not** committed. Please download NASA C-MAPSS (FD001–FD004) separately and place them under `data/raw/` using the expected folder names.

---

## Quick start

### 1) Create the environment
```bash
conda env create -f environment.yml
conda activate rul-dms
```

### 2) Data layout
Place C-MAPSS subsets under:
```
data/raw/FD001
data/raw/FD002
data/raw/FD003
data/raw/FD004
```

### 3) Run notebooks
Open the notebooks in `notebooks/` and execute top-to-bottom. Each notebook contains cell-level comments explaining preprocessing, model training, ensembling, and evaluation. Figures and tables will be (re)generated inside `results/`.

---

## Results (artifacts)
All figures and CSVs used in the paper have been organized under `results/`. Subfolders reflect the corresponding C-MAPSS subset (FD001–FD004). The repository **does not** bundle raw data; only derived, publishable artifacts.

---

## Reproducibility notes
- **Randomness**: set seeds where supported by the libraries (see notebook headers).
- **Hardware**: commodity CPU is sufficient; GPU not required for tree ensembles.
- **Versions**: `environment.yml` pins major package versions for consistent runs.
- **Large files**: if trained models exceed GitHub’s size limit, use Git LFS or upload to Zenodo/OSF and reference a DOI here.

---

## Citing
If you use this repository, please cite the paper and this code release.

```bibtex
@misc{ozcan_rul_dms_2025,
  author = {{Hikmetcan Özcan}},
  title  = {{Interpretable Ensemble Remaining Useful Life Prediction Enables Dynamic Maintenance Scheduling for Aircraft Engines}},
  year   = {{2025}},
  howpublished = {GitHub repository},
  url    = {REPO_URL_HERE}
}
```

---

## License
- **Code**: MIT License (see `LICENSE`)
- **Figures & derived datasets** (CSV/PNG/PDF under `results/`): Creative Commons **CC BY 4.0**.
- **Upstream raw data**: follow the original dataset’s terms; do **not** redistribute proprietary or restricted files in this repo.
