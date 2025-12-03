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

```apa
Özcan, H. Interpretable ensemble remaining useful life prediction enables dynamic maintenance scheduling for aircraft engines. Sci Rep 15, 39795 (2025). https://doi.org/10.1038/s41598-025-23473-2
}
```



```ris
TY  - JOUR
AU  - Özcan, Hikmetcan
PY  - 2025
DA  - 2025/11/13
TI  - Interpretable ensemble remaining useful life prediction enables dynamic maintenance scheduling for aircraft engines
JO  - Scientific Reports
SP  - 39795
VL  - 15
IS  - 1
AB  - This study introduces a predictive-maintenance framework for aircraft engines that integrates accurate remaining-useful-life (RUL) estimation with a cost-aware scheduling strategy. The predictive layer employs ensemble learning by combining LightGBM, CatBoost, and Gradient Boosting, thereby enhancing both accuracy and stability. The scheduling layer initiates maintenance once the predicted RUL falls below a tunable threshold $$\tau$$(set to 15 cycles in experiments) and allocates service slots under cost and risk tolerance constraints, ensuring flexibility for conservative operation when necessary. The framework is evaluated on the NASA C-MAPSS dataset (FD001–FD004), covering single- and multi-condition as well as single- and multi-fault scenarios. Experimental results demonstrate strong performance on FD001 and FD003, with competitive results on FD002 and FD004. For instance, the LightGBM+CatBoost ensemble achieves RMSE = 6.62 and RUL Score = $$2.951 \times 10^{3}$$on FD001, while the three-model ensemble yields RMSE = 9.71 and RUL Score = $$1.037 \times 10^{4}$$on FD003. To ensure transparency and reliability, SHAP-based interpretability analysis is applied, highlighting critical sensors and operational cycles. The ensemble approach provides more balanced attributions, which enhances auditability and supports engineering validation in safety-critical domains. Overall, this study contributes to aviation predictive maintenance by delivering robust and interpretable RUL predictions and by translating them into tunable maintenance policies; however, these contributions are demonstrated on C-MAPSS and with a fixed illustrative threshold, so the reported gains should be interpreted as benchmark-specific until confirmed on real fleets and under alternative risk-aware policies.
SN  - 2045-2322
UR  - https://doi.org/10.1038/s41598-025-23473-2
DO  - 10.1038/s41598-025-23473-2
ID  - Özcan2025
ER  - 

```


```bibtex
@article{Ozcan2025InterpretableRUL,
  author    = {Özcan, H.},
  title     = {Interpretable ensemble remaining useful life prediction enables dynamic maintenance scheduling for aircraft engines},
  journal   = {Scientific Reports},
  year      = {2025},
  volume    = {15},
  pages     = {39795},
  doi       = {10.1038/s41598-025-23473-2}
}

```

```bibitem
\bibitem{Ozcan2025}
H.~Özcan, ``Interpretable ensemble remaining useful life prediction enables dynamic maintenance scheduling for aircraft engines,'' \emph{Scientific Reports}, vol.~15, p.~39795, 2025. doi: 10.1038/s41598-025-23473-2.
```

---

## License
- **Code**: MIT License (see `LICENSE`)
- **Figures & derived datasets** (CSV/PNG/PDF under `results/`): Creative Commons **CC BY 4.0**.
- **Upstream raw data**: follow the original dataset’s terms; do **not** redistribute proprietary or restricted files in this repo.
