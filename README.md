# 🛢️ Oil Well Profitability & Risk Analysis

Machine learning analysis for oil well selection, profitability estimation, and investment risk assessment using **Linear Regression** and **Bootstrapping**.

## 📌 Context

Oil exploration involves significant financial investment and uncertainty. Choosing where to develop new wells requires more than identifying locations with large estimated reserves — it is also necessary to evaluate profitability and the risk of financial loss.

In this project, geological exploration data from three different regions was analyzed to determine which region offers the most attractive combination of **predicted oil reserves, expected profit, and investment risk**.

The project was developed as part of my Data Science studies and reorganized for portfolio presentation.

## 🎯 Problem

The objective is to identify the most suitable region for developing new oil wells.

The business process follows these conditions:

- 500 potential wells are evaluated in each exploration;
- the 200 wells with the highest predicted reserves are selected;
- the available budget for developing 200 wells is **$100 million**;
- one unit of product represents one thousand barrels;
- each unit of product generates **$4,500 in revenue**;
- only regions with a risk of loss below **2.5%** should be considered.

The challenge is therefore not only to predict oil reserves, but also to translate model predictions into a financially informed investment decision.

## 📊 Dataset

The analysis uses geological exploration data from three regions:

- `geo_data_0.csv`
- `geo_data_1.csv`
- `geo_data_2.csv`

Each dataset contains the following variables:

- `id` — unique identifier for each oil well;
- `f0`, `f1`, `f2` — geological features associated with each location;
- `product` — volume of oil reserves in thousands of barrels.

## 🔎 Approach

The project follows a structured machine learning and business analysis workflow:

1. Data loading and inspection
2. Data preparation
3. Train-validation split
4. Linear Regression modeling
5. Model evaluation using RMSE
6. Prediction of oil reserves
7. Break-even reserve calculation
8. Selection of the 200 wells with the highest predicted reserves
9. Profit estimation
10. Bootstrapping with 1,000 samples
11. Confidence interval estimation
12. Risk-of-loss calculation
13. Final region comparison

## 🤖 Machine Learning Model

A **Linear Regression** model was trained independently for each of the three regions.

Each dataset was divided into:

- **75% training data**
- **25% validation data**

Model performance was evaluated using **Root Mean Squared Error (RMSE)**, while the average predicted reserve volume was also compared across regions.

This comparison illustrates an important machine learning trade-off: a region may show larger predicted reserves while another may provide more accurate predictions.

## 💰 Profitability Analysis

The business assumptions were translated into variables used throughout the analysis.

With a total investment of **$100 million** distributed across **200 wells**, each selected well must generate approximately **$500,000 in revenue** to reach the break-even point.

Given the revenue of **$4,500 per unit of product**, the required average reserve is approximately:

**111.1 thousand barrels per well**

The predicted reserves were then used to rank candidate wells, and the 200 locations with the highest predictions were selected for each region.

Profit was calculated using the actual reserve volumes associated with those selected wells.

## 🎲 Risk Analysis with Bootstrapping

Selecting wells based only on their highest predicted reserves does not fully represent the uncertainty involved in exploration.

To estimate investment risk, **Bootstrapping with 1,000 simulations** was applied.

For each simulation:

- 500 wells were sampled;
- the model predictions were used to select the 200 most promising wells;
- profit was calculated using their actual reserve volumes.

The resulting profit distributions were used to estimate:

- average expected profit;
- 95% confidence interval;
- probability of financial loss.

This makes it possible to compare regions not only by potential return, but also by uncertainty and downside risk.

## 💡 Key Findings

The analysis demonstrates why model predictions should be combined with financial and risk analysis.

Some important observations include:

- average reserve volume alone is not sufficient for selecting an investment region;
- prediction accuracy differs considerably between regions;
- selecting wells using predicted reserves can generate substantial potential profit;
- the region with the highest deterministic profit is not necessarily the best option after uncertainty is considered;
- Bootstrapping provides a more realistic perspective on potential financial outcomes;
- risk constraints can materially change the final business decision.

Under the defined business rule requiring a probability of loss below **2.5%**, the risk analysis identifies **Region 1** as the recommended region for development.

## 🚀 Business Applications

This analytical framework illustrates how machine learning can support capital allocation decisions by combining:

- predictive modeling;
- resource estimation;
- profitability analysis;
- scenario simulation;
- uncertainty quantification;
- risk-based decision making.

Similar approaches can be applied to investment prioritization, site selection, resource allocation, and other business problems where decisions must balance expected returns and uncertainty.

## ⚠️ Limitations

The datasets used in this project are synthetic and do not contain detailed geological, operational, contractual, or market information.

The analysis also assumes:

- a fixed development budget;
- constant revenue per unit of oil;
- no variation in operating or drilling costs between wells;
- Linear Regression as the required prediction model;
- historical sample behavior as the basis for the Bootstrapping simulations.

Therefore, the results should be interpreted as a demonstration of a machine learning decision framework rather than a real-world oil exploration recommendation.

## 🛠️ Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Linear Regression
- Bootstrapping
- Jupyter Notebook

## 📁 Repository Structure

```text
oil-well-profitability-analysis/
│
├── README.md
│
├── data/
│   ├── geo_data_0.csv
│   ├── geo_data_1.csv
│   └── geo_data_2.csv
│
└── notebook/
    └── oil_well_profitability_analysis.ipynb
```

## ▶️ Running the Project

Clone the repository and open the Jupyter Notebook located in the `notebook` directory.

The datasets used by the notebook are stored in the `data` directory.

The analysis requires **Python**, **Pandas**, **NumPy**, **Matplotlib**, and **Scikit-learn**.

---

### Author

**Brunno Almeida**

Data Science | Data Analytics | Python | SQL | Machine Learning
