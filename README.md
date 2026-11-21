# Marketing Campaign Response — Logistic Regression (STAT 301)

UBC **STAT 301** group project (G11).

Predicts whether a customer will accept the next marketing-campaign offer using logistic regression on a customer personality dataset (2,240 customers, 29 variables).

**Group:** Sean Liu · Carlo Magaoay · Samantha Cham · Prabhnoor Karwal

## Question

What is the probability a customer accepts the next campaign offer, and which factors matter most?

## Findings (short)

| Result | Detail |
|--------|--------|
| Method | Logistic regression + stepwise selection (`stepAIC`, BIC, both directions) |
| Train / test | 70 / 30 stratified split (`Response`) |
| Test AUC | **0.870** |
| Strongest signals | Past campaign accepts ↑ odds; `Teenhome` ↓ odds; higher `Recency` ↓ odds |
| Practical threshold | ~**17%** predicted probability (balances TPR / FPR on the ROC) |

**Takeaway:** Past response behaviour is highly informative. A ~17% cutoff is more useful than 50% because accept rates are only ~15%.

## What’s in this repo

| File | Purpose |
|------|---------|
| `marketing_campaign.csv` | Customer personality / campaign dataset (tab-separated) — **do not rename/move** (notebook loads it from this GitHub path) |
| `marketing_campaign_logistic_regression.ipynb` | Full assignment: EDA, model, ROC, interpretation |
| `README.md` | Recruiter-facing project summary |

## How to explore (recruiters)

Open the notebook on GitHub — no install needed. Skim Section 2 (question), the EDA bar chart, then the ROC / AUC output near the end.

## How to run locally (optional)

Needs **R** + Jupyter with these packages:

```r
install.packages(c("tidyverse", "rsample", "broom", "pROC", "MASS", "IRkernel"))
```

Then open `marketing_campaign_logistic_regression.ipynb` and run all cells.

The notebook loads the CSV from this repo’s GitHub URL (reproducible; no local path required).

## Stack

R · tidyverse · glm (logistic) · MASS::stepAIC · rsample · broom · pROC · Jupyter

## Data credit

Patel, A. “Customer Personality Analysis.” Kaggle.  
https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis  
Dataset provided by Dr. Omar Romero-Hernandez (as acknowledged on the source page).

## Notes

AI tools were used to debug code and get wording feedback. I can explain every part of the analysis.

## Suggested GitHub About blurb

> STAT 301 — logistic regression for marketing campaign response (AUC 0.87, ROC thresholding)

**Topics:** `r` `statistics` `logistic-regression` `marketing` `roc` `tidyverse` `ubc` `jupyter`
