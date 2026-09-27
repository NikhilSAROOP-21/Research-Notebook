<div align="center">

# 🎓 RPDA8412 Research Project

### Comparing Interpretable Machine Learning Models for Early Higher Education Dropout Prediction

![Python](https://img.shields.io/badge/python-3.10%2B-blue?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/notebook-Jupyter-orange?logo=jupyter&logoColor=white)
![scikit--learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikitlearn&logoColor=white)
![SHAP](https://img.shields.io/badge/interpretability-SHAP%20%7C%20LIME%20%7C%20DiCE-6A5ACD)
![Status](https://img.shields.io/badge/status-in%20progress-yellow)
![License](https://img.shields.io/badge/license-academic%20use-lightgrey)

**Nikhil Saroop** · Student No. **ST10040092**
The Independent Institute of Education (IIE), Varsity College — Postgraduate Diploma in Data Analytics

</div>

---

## 📑 Table of Contents

- [Overview](#-overview)
- [Research Questions](#-research-questions)
- [Hypotheses](#-hypotheses)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
- [Project Phases](#-project-phases)
- [Key Outputs](#-key-outputs)
- [Repository Structure](#-repository-structure)
- [Tech Stack](#️-tech-stack)
- [Getting Started](#-getting-started)
- [Results](#-results)
- [Limitations](#-limitations)
- [Author](#-author)
- [Acknowledgements](#-acknowledgements)

---

## 📖 Overview

This repository contains the full implementation of a quantitative, secondary-data research study investigating **early prediction of higher education dropout risk**. The study compares three machine learning models — **Logistic Regression**, **Random Forest**, and **Gradient Boosting** — across three progressively information-rich prediction stages: pre-enrolment, post-first-semester, and post-second-semester.

Beyond raw predictive performance, the project places strong emphasis on **interpretability**, using SHAP, LIME, and counterfactual explanations (DiCE) to evaluate how well model decisions can be understood and trusted by non-technical higher education practitioners.

The analysis follows a reproducible, evidence-based workflow that distinguishes between:

| Decision Type | Description |
|---|---|
| 🔒 **Pre-specified** | Methodological commitments fixed in the approved research proposal, before modelling began |
| 🔬 **Evidence-based** | Implementation decisions made only after examining the dataset |
| 📊 **Findings** | Outcomes produced by the completed analysis |

This distinction reduces the risk of methodology drift in response to preferred results, and provides a transparent record of how the study was conducted (Romero & Ventura, 2020).

---

## 🔍 Research Questions

| # | Question |
|---|---|
| **RQ1** | How do Logistic Regression, Random Forest, and Gradient Boosting compare in predicting student dropout risk across pre-enrolment, post-first-semester, and post-second-semester prediction stages? |
| **RQ2** | Which academic, demographic, socioeconomic, and macroeconomic features are the strongest predictors of dropout risk at each stage, and how does feature importance shift as semester performance information becomes available? |
| **RQ3** | To what extent can SHAP-based explanations provide clear, consistent, and practically useful insight into dropout-risk predictions for non-technical higher education practitioners? |

## 🧪 Hypotheses

| # | Hypothesis | Related RQ |
|---|---|:---:|
| **H1** | Gradient Boosting and Random Forest are expected to outperform Logistic Regression across the three prediction stages, as ensemble models can capture non-linear interactions among student features. | RQ1 |
| **H2** | Model performance is expected to improve from Stage 1 to Stage 3, as semester-level academic performance data progressively increases the information available to the models. | RQ1 |
| **H3** | Academic performance indicators are expected to become more important than demographic and socioeconomic indicators from Stage 2 onward, as reflected in SHAP feature rankings. | RQ2 |
| **H4** | SHAP explanations are expected to provide transparent, feature-level insight that supports non-technical interpretation of model predictions. | RQ3 |

---

## 📊 Dataset

| Attribute | Detail |
|---|---|
| **Source** | Realinho et al. (2022), *"Predict Students' Dropout and Academic Success"* |
| **Repository** | UCI Machine Learning Repository |
| **Domain** | Higher education, student retention |
| **Feature categories** | Academic (prior & in-programme), demographic, socioeconomic, macroeconomic |
| **Target** | Student outcome, mapped to a binary dropout / non-dropout label |
| **Granularity** | Per-student record, enriched with first- and second-semester performance |

### Prediction Stages

| Stage | Checkpoint | Information Available |
|---|---|---|
| **Stage 1** | Pre-enrolment | Demographic, socioeconomic, macroeconomic, and prior academic data only |
| **Stage 2** | Post-first-semester | Stage 1 features + first-semester academic performance |
| **Stage 3** | Post-second-semester | Stage 2 features + second-semester academic performance |

---

## 🧠 Methodology

- **Three-stage prediction framework** — models trained and evaluated separately at each checkpoint, reflecting how information accumulates over a student's early academic journey.
- **Model comparison** — Logistic Regression, Random Forest, and Gradient Boosting, with hyperparameter tuning, cross-validated baselines, and class-imbalance handling (SMOTENC).
- **Interpretability toolkit** — global and local SHAP explanations, LIME comparisons, and DiCE counterfactuals to assess actionability and consistency of model reasoning.
- **Robustness checks** — bootstrap confidence intervals, calibration analysis, subgroup/fairness performance gaps, and partial dependence analysis.
- **Practical translation** — risk-tier stratification and practitioner-facing explanation tables to bridge model output and real-world decision-making.

## 🗂️ Project Phases

<details>
<summary><strong>Click to expand the full phase-by-phase pipeline</strong></summary>

| Phase | Focus |
|---|---|
| 0 | Pre-analysis research protocol & pre-specified methodological commitments |
| 2 | Dataset provenance and sourcing |
| 4 | Data quality profiling |
| 5 | Preprocessing decision register & modelling feature dictionary |
| 6 | Exploratory data analysis on the original multi-class target |
| 7 | Binary target construction & mapping |
| 8 | Exploratory data analysis on the binary dropout target |
| 9 | Prediction-stage membership assignment |
| 10 | Shared stratified train/test split |
| 11 | Preprocessing pipeline construction & audit (scaling, passthrough checks) |
| 12 | Cross-validated baseline modelling |
| 13 | Hyperparameter tuning & locked configurations |
| 14 | Class-imbalance handling with SMOTENC |
| 15 | Decision-threshold selection |
| 16 | Final held-out evaluation, ROC curves, bootstrap confidence intervals |
| 17 | Global SHAP interpretability & feature-group importance |
| 18 | Local SHAP explanations & practitioner-facing case studies |
| 19 | Calibration, LIME, DiCE counterfactuals, subgroup fairness analysis |
| 20 | Partial dependence, risk-tier stratification, final confusion matrices |
| 21 | Final synthesis, hypothesis assessment, and research alignment |

</details>

---

## 📦 Key Outputs

| File | Description |
|---|---|
| `outputs/tables/phase16_final_test_results.csv` | Final held-out performance metrics for all models and stages |
| `outputs/tables/phase16_final_roc_auc_ranking.csv` | ROC-AUC ranking across models and stages |
| `outputs/tables/phase16_bootstrap_metric_confidence_intervals.csv` | Bootstrap confidence intervals for key metrics |
| `outputs/tables/phase17_stage_consensus_shap.csv` | Consensus SHAP feature importance per stage |
| `outputs/tables/phase17_shap_group_importance.csv` | SHAP importance aggregated by feature group |
| `outputs/tables/phase18_practitioner_explanation_table.csv` | Practitioner-facing local explanation summaries |
| `outputs/tables/phase19_dice_counterfactual.csv` | DiCE counterfactual recommendations |
| `outputs/tables/phase19_subgroup_performance.csv` | Subgroup / fairness performance breakdown |
| `outputs/tables/phase20_risk_tier_summary.csv` | Risk-tier stratification summary |
| `outputs/tables/phase21_final_hypothesis_assessment.csv` | Final assessment of H1–H4 against the evidence |
| `outputs/figures/phase16_stage_3_heldout_roc.png` | Held-out ROC curve, Stage 3 |
| `outputs/figures/phase17_stage_3_consensus_shap.png` | Consensus SHAP summary plot, Stage 3 |
| `outputs/figures/phase20_final_locked_confusion_matrices.png` | Final confusion matrices, all models/stages |

> Full outputs are in [`outputs/tables/`](outputs/tables) and [`outputs/figures/`](outputs/figures); trained models are in [`outputs/models/`](outputs/models). `outputs_previous/` retains the prior run for comparison.

---

## 📁 Repository Structure

```
Research Notebook/
├── data/
│   └── raw/                     # Source dataset
├── docs/                        # Supporting documentation
├── notebooks/
│   └── ST10040092_RPDA8412_Research_Analysis.ipynb
├── outputs/
│   ├── figures/                 # ROC curves, SHAP plots, calibration, PDPs
│   ├── models/                  # Final trained models (.joblib)
│   └── tables/                  # Metrics, SHAP values, thresholds, results
├── outputs_previous/            # Prior run's outputs (retained for comparison)
├── src/
│   ├── __init__.py
│   └── utils.py
├── .gitignore
├── README.md
└── requirements.txt
```

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| **Language / Environment** | Python 3.10+, Jupyter Notebook |
| **Modelling** | scikit-learn |
| **Data handling** | pandas, NumPy |
| **Visualisation** | seaborn, matplotlib |
| **Statistics** | statsmodels |
| **Interpretability** | SHAP, LIME, DiCE |
| **Imbalance handling** | imbalanced-learn (SMOTENC) |
| **Model persistence** | joblib |

---

## 🚀 Getting Started

### Prerequisites

| Requirement | Version |
|---|---|
| Python | 3.10+ |
| Jupyter Notebook | Latest |

### Installation

```bash
# Clone the repository
git clone https://github.com/NikhilSAROOP-21/RPDA8412-Research-Project.git
cd RPDA8412-Research-Project

# Create and activate a virtual environment
python -m venv .venv
source .venv/Scripts/activate      # Windows (Git Bash)
# .venv\Scripts\activate.bat       # Windows (Command Prompt)
# source .venv/bin/activate        # macOS/Linux

# Install dependencies
pip install -r requirements.txt
```

### Usage

```bash
jupyter notebook notebooks/ST10040092_RPDA8412_Research_Analysis.ipynb
```

---

## 📈 Results

<details>
<summary><strong>Model performance (see notebook & tables for full figures)</strong></summary>

Full results are reported in the notebook and in `outputs/tables/`, including:

- ROC-AUC ranking of Logistic Regression, Random Forest, and Gradient Boosting across all three stages
- Bootstrap confidence intervals for all key metrics
- Calibration curves per model at Stage 3
- Held-out confusion matrices for the final locked models

</details>

<details>
<summary><strong>Interpretability findings</strong></summary>

- Global and local SHAP explanations, with consensus feature rankings per stage
- SHAP feature-group importance (academic vs. demographic vs. socioeconomic vs. macroeconomic)
- LIME comparisons for local explanation consistency
- DiCE counterfactuals showing actionable changes for at-risk students
- Practitioner-facing explanation tables translating SHAP output into plain language

</details>

<details>
<summary><strong>Robustness & fairness</strong></summary>

- Subgroup performance gaps across demographic and socioeconomic groups
- Partial dependence analysis for top predictive features
- Risk-tier stratification linking predicted probability to practical response categories

</details>

---

## ⚠️ Limitations

A full limitation register is maintained in [`outputs/tables/phase21_final_limitation_register.csv`](outputs/tables/phase21_final_limitation_register.csv), covering known constraints such as dataset scope, generalisability beyond the source institution, and the boundaries of SHAP-based interpretability claims.

---

## 👤 Author

**Nikhil Saroop**
Postgraduate Diploma in Data Analytics, The IIE Varsity College, Durban

## 📚 Acknowledgements

- Realinho, V. et al. (2022). *Predict Students' Dropout and Academic Success* [dataset]. UCI Machine Learning Repository.
- Romero, C. & Ventura, S. (2020). Educational data mining and learning analytics research.
