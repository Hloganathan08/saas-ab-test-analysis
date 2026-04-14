# SaaS Onboarding A/B Test Analysis

A complete product experiment analysis measuring the impact of a redesigned onboarding flow on 30-day user activation rates. Includes statistical testing, confidence intervals, effect size, power analysis, business impact projection, and an executive decision memo.

---

## Experiment Summary

| Metric | Value |
|--------|-------|
| Experiment duration | 28 days (Jan 6 – Feb 3, 2026) |
| Total users | 5,738 |
| Control group | 2,847 users — original onboarding flow |
| Treatment group | 2,891 users — redesigned flow with progress bar + tooltips |
| Control activation rate | 32.1% |
| Treatment activation rate | 37.8% |
| Absolute lift | **+5.7 percentage points** |
| Relative lift | **+17.7%** |
| **Decision** | ✅ **SHIP** |

---

## Statistical Results

| Test | Result |
|------|--------|
| Method | Two-proportion z-test |
| Z-statistic | 4.50 |
| P-value (two-tailed) | < 0.001 |
| 95% Confidence Interval | [+3.2%, +8.1%] |
| Cohen's h (effect size) | 0.119 (small) |
| Statistical power | 99.8% |
| Significant at α = 0.05 | ✅ Yes |
| Significant at α = 0.01 | ✅ Yes |

The 95% CI excludes zero entirely. Results are not attributable to chance.

---

## Business Impact

| Assumption | Value |
|-----------|-------|
| Monthly new signups | 12,000 |
| Additional activations/month | ~680 users |
| Avg annual contract value | $4,800 |
| Projected annual revenue lift | **$3.26M** |
| Cumulative 12-month impact | **$39.2M** |

---

ab_test_project/
├── ab_test_analysis.ipynb       ← Full analysis notebook (Python)
├── AB_Test_Decision_Memo.pdf    ← 1-page executive decision memo
├── data/
│   └── experiment_users.csv     ← 5,738 user-level records
└── output/
├── ab_test_results.png      ← 4-chart dashboard
├── ab_test_summary.csv      ← Key metrics summary
└── ab_test_users.csv        ← Processed user data for BI tools

---

## Analysis Approach

**Data generation** — Synthetic but realistic dataset simulating a 28-day SaaS onboarding experiment. User-level records include signup date, group assignment, activation status, time-to-activate, and session counts.

**Statistical testing** — Two-proportion z-test. One-tailed test for directional hypothesis (treatment > control), two-tailed p-value reported for conservatism. Pooled standard error under H0.

**Confidence interval** — Unpooled standard error for the CI of the difference in proportions, 1.96 critical value at 95% confidence.

**Effect size** — Cohen's h applied to arcsine-transformed proportions, appropriate for comparing two independent proportions.

**Power analysis** — Post-hoc power computed from observed z-statistic and α = 0.05. Pre-registered MDE was 2.0 percentage points at 80% power.

**Business impact** — Linear projection from monthly signup volume × observed lift × average annual contract value. Assumes no seasonality or novelty effects.

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/Hloganathan08/saas-ab-test-analysis.git
cd saas-ab-test-analysis

# Install dependencies
pip install pandas numpy scipy matplotlib seaborn jupyter

# Run the notebook
jupyter notebook ab_test_analysis.ipynb
```

---

## Stack

| Tool | Purpose |
|------|---------|
| Python (pandas, numpy, scipy) | Data generation and statistical testing |
| matplotlib, seaborn | Visualization |
| reportlab | PDF decision memo generation |
| Jupyter Notebook | Analysis environment |

---

## About

**Harshita Loganathan** — Data Analyst
- 🔗 [LinkedIn](https://linkedin.com/in/harshitaloganathan)
- 💻 [GitHub](https://github.com/Hloganathan08)
- 🏥 [Healthcare Market Risk Analysis](https://github.com/Hloganathan08/hospital-market-risk-analysis)
- 🏔️ [dbt Snowflake Analytics Layer](https://github.com/Hloganathan08/dbt-ecommerce-snowflake)
