# Intersectional Hiring Audit

An intersectional self-audit framework for hiring models, checking **behavioural** and **activation-space** bias on race × age. Built for the 180DC Bristol × BDSS datathon "Exploring Bias in Hiring" (7 Oct 2026).

> Status: framework + design complete; Tier 1 experiment in progress. See `docs/EXPERIMENT_DESIGN.md`. Results sections below are filled in once real numbers exist.

## Problem
Hiring-model audits usually test one protected attribute at a time. Hannah Liu's thesis ("Evaluating Weight-Level Bias Mitigation Against Behavioral and Activation-Space Bias", Imperial) shows that removing behavioural bias does not remove activation-space bias, and that results are model-dependent. It tests race only. Real candidates are intersectional.

## Hypothesis
Race and age bias directions found separately differ from those found jointly (H1 superposition, H2 interaction effect, H3 mitigation leakage). A single-axis audit could pass a model that is still biased at the intersection.

## Method
2×2 counterfactual: same resume and job, vary only name (race proxy) × dates (age proxy). Measure shortlisting gap per cell, interaction residual, and per-layer difference-of-means bias directions (cosines, norms). Full design: [`docs/EXPERIMENT_DESIGN.md`](docs/EXPERIMENT_DESIGN.md).

## Datasets
- Resume dataset (Kaggle, 2,484 resumes, 24 categories): base resumes with names/dates scrubbed and re-inserted.
- [`datastax/linkedin_job_listings`](https://huggingface.co/datasets/datastax/linkedin_job_listings) (~124k postings): sampled and matched to resume category.

Data files are not committed; place them under `data/` (`data/raw/Resume/Resume.csv`, `data/jobs/postings.csv`).

## Results
_Pending Tier 1 run._

## Sociotechnical risks
Names and dates are imperfect proxies; probe confounds; we can only fail to find bias, not certify its absence; fairwashing risk; human oversight is required; re-audit on every model change; only race and age are covered.

## How to run
```
pip install -r requirements.txt
python src/run_tier1.py   # coming
```

## Website
https://bias-lens-fairness.lovable.app/
