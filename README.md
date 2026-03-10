# Election-Year Effects in VIX Returns

## Overview

This repository examines whether U.S. presidential election years are associated with systematic changes in implied volatility during October. The analysis focuses on the CBOE Volatility Index (VIX) and tests whether October returns differ between election and non-election years.

The project applies standard empirical finance techniques including regression analysis and bootstrap inference to evaluate whether a consistent relationship exists in historical data.

The goal of the study is not to propose a trading strategy, but to evaluate whether a politically driven volatility pattern can be detected using publicly observable data.

------------------------------------------------------------------------

## Research Question

Do U.S. presidential election years exhibit different October VIX return behavior compared with non-election years?

The hypothesis is motivated by the possibility that political uncertainty leading into elections may affect market expectations of volatility.

------------------------------------------------------------------------

## Data

The dataset contains historical VIX index levels sourced from Bloomberg.

Variables include:

-   Daily VIX closing values
-   Calendar dates
-   Election year indicator
-   Derived October return measures

October returns are calculated using end-of-September and end-of-October VIX levels for each year in the sample.

Because Bloomberg data is proprietary, a processed dataset containing the variables necessary to reproduce the analysis is included in the repository.

------------------------------------------------------------------------

## Methodology

The analysis proceeds in several steps:

1.  **Data preparation**

-   Construct annual October VIX returns
-   Identify election years
-   Create summary statistics for both groups

2.  **Regression analysis**

Estimate the following model:

$$
R^{Oct}_t = \alpha + \beta ElectionYear_t + \varepsilon_t
$$

where `ElectionYear` is a binary indicator for U.S. presidential election years.

3. **Controlled regression**

Additional specifications include controls for lagged volatility and prior VIX levels.

4. **Bootstrap inference**

A bootstrap procedure is used to evaluate the stability of the estimated election-year effect under repeated resampling.

---

## Results

The analysis compares average October VIX returns between election and non-election years and evaluates whether the difference is statistically distinguishable from zero.

Regression results and bootstrap simulations provide evidence on the magnitude and stability of any observed effect.

Full model outputs and figures are generated within the research notebook.

---

## Repository Structure

```
election-year-vix-study
│
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
│
├── notebooks
│   └── vix_election_trade.ipynb
│
└── data
    └── raw/vix_data_sample.csv
```

---

## Reproducing the Analysis

Install dependencies:

pip install -r requirements.txt


Then run the notebook:

jupyter notebook notebooks/vix_election_trade.ipynb


All figures and regression outputs will be generated within the notebook.

---

## Limitations

The sample of election years is limited, and results should therefore be interpreted cautiously. The analysis focuses on historical patterns and does not attempt to forecast future volatility behavior.

---

## Disclaimer

This repository is intended for research and educational purposes only. It does not constitute investment advice.







