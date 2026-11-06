<div align="center">

# 📱 App User Behavior Segmentation

### Discovering patterns in app usage with unsupervised machine learning

A beginner-friendly project using **K-Means clustering** to explore how users interact with an app, profile behavioral groups, and suggest actions for improving engagement.

[📓 Open the notebook](./App_User_Segmentation.ipynb) · [📄 Read the project report](./App_User_Behavior_Segmentation_Report%20%282%29.pdf)

</div>

---

## Project at a glance

| Dataset | Method | Features | Groups explored |
|:--|:--|:--|:--|
| 50,000 app users | K-Means | 7 behavior measures | 4 requested clusters |

### The key finding

The four-group model assigns every user to a segment, but the groups overlap considerably. The sampled silhouette score is **0.104**, so these should be treated as exploratory groups, not proven customer types. The analysis finds clearer differences in session length, pages viewed, and login recency than in average engagement or the supplied churn-risk score.

> **Why include this finding?** A clustering algorithm always returns groups when asked. We should check whether the dataset actually supports them before drawing business conclusions.

## Project workflow

The notebook follows the ten steps in the project brief:

1. Data collection and loading
2. Data understanding
3. Data cleaning and missing-value treatment
4. Behavior feature selection
5. Standardization with `StandardScaler`
6. K-Means model selection
7. Elbow and silhouette comparison for K = 1 to 10
8. Cluster assignment and PCA visualization
9. Cluster profiling and user identification
10. Business insights and suggested actions

## Files

| File | What it contains |
|:--|:--|
| [`App_User_Segmentation.ipynb`](./App_User_Segmentation.ipynb) | Step-by-step analysis, code, explanations, and outputs |
| [`App_User_Behavior_Segmentation_Report (2).pdf`](./App_User_Behavior_Segmentation_Report%20%282%29.pdf) | Formatted project report with findings, charts, and limitations |

## Run the notebook in Google Colab

1. Open [the notebook](./App_User_Segmentation.ipynb) and choose **Open in Colab** (or download it and upload it to Colab).
2. Upload `app_user_behavior_dataset.csv` in Colab's **Files** panel. The notebook expects this exact filename in its working folder.
3. Select **Runtime → Run all**.
4. Open the generated `outputs` folder to view the charts and user-level segment files.

Install the libraries listed in the notebook if prompted:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn threadpoolctl ipython
```

## How the analysis works

**Prepare behavior data.** The project uses sessions per week, average session duration, daily active minutes, feature clicks, pages viewed, days since last login, and the supplied engagement score. User IDs and categories are left out of the first model.

**Scale the features.** Standardization puts differently sized measurements on comparable scales because K-Means uses distances between users.

**Compare cluster counts.** The elbow chart shows how the within-cluster distance changes as K increases. The silhouette score gives a separate check of how well-separated the groups appear.

**Profile and interpret.** Cluster numbers are identifiers. The notebook ranks groups for the requested High, Moderate, Occasional, and Low / At-Risk labels, then shows the actual behavioral averages behind each label.

## Important interpretation notes

- The four labels are provisional relative labels. “Occasional” does not prove irregular visits, and “At-Risk” does not predict churn.
- The supplied `churn_risk_score` is not a verified churn outcome; its formula and calibration are not provided.
- The engagement-score formula is also unknown.
- The retention and loyalty review thresholds are illustrative business rules, not validated predictions.
- Revenue and actual churn outcomes are not included, so the project cannot prove customer value or campaign impact.

## Tools

**Python** · **Pandas** · **NumPy** · **Matplotlib** · **Seaborn** · **scikit-learn**

---

<div align="center">

Made as a beginner-friendly data science project · Questions and suggestions are welcome

</div>
