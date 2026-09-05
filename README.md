# Seasonal Agriculture Performance Analysis

A data analytics project analyzing seasonal agricultural performance across Indian states, crops, and seasons (Kharif, Rabi, Zaid) to uncover meaningful patterns, trends, and relationships in yield, resource usage, and economic outcomes.

## Problem Statement

Agricultural performance is influenced by seasonal variations in environmental conditions, farming practices, resource availability, and market conditions. Raw agricultural data does not clearly reveal how performance changes across seasons. This project analyzes a seasonal agriculture dataset to identify meaningful patterns, trends, relationships, and variations, in order to support evidence-based agricultural planning.

## Dataset

`seasonal_agriculture_performance_dataset.csv`

- **4,000 farm records**
- **8 states**, **8 crops**, **3 seasons** (Kharif, Rabi, Zaid)
- 28 columns covering:
  - **Environmental conditions**: rainfall, temperature, humidity, sunlight hours, soil pH, soil moisture
  - **Resource usage**: water used, water efficiency, fertilizer, pesticide, N-P-K levels, irrigation method
  - **Farming inputs**: farm area, seed quality score
  - **Yield & production**: yield (t/ha), production (tonnes)
  - **Economics**: market price, total cost, revenue, profit
  - **Risk**: disease/pest risk (%)

## Project Structure

```
.
├── Seasonal_Agriculture_Performance_Analysis.ipynb   # Full analysis notebook
├── seasonal_agriculture_performance_dataset.csv      # Dataset
└── README.md
```

## Tech Stack

- **Language**: Python
- **Data handling**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Statistics**: SciPy (ANOVA, correlation analysis)
- **Environment**: Jupyter Notebook

## Approach

1. **Data cleaning** - handled missing values (season-wise median imputation), checked for duplicates and invalid ranges
2. **Feature engineering** - derived profit margin (%) and cost per tonne
3. **Seasonal comparison** - yield, environmental conditions, resource usage, and economics compared across Kharif, Rabi, and Zaid
4. **Statistical testing** - one-way ANOVA to test whether yield differences across seasons are statistically significant
5. **Correlation analysis** - identified which environmental/resource factors most strongly drive yield and profit
6. **Regional analysis** - state × season yield heatmap to check whether seasonal patterns are consistent across states

## Key Findings

- **Yield differs numerically across seasons** (Kharif > Rabi > Zaid on average), but the difference is **not statistically significant** (ANOVA p ≈ 0.21). The yield distribution is also heavily right-skewed (median ≈ 1.74 t/ha vs. mean ≈ 5.27 t/ha), meaning a small number of high-yield outliers pull the seasonal averages up.
- **Water efficiency is the strongest driver of yield** (correlation ≈ 0.91), far ahead of rainfall, nutrients, or pesticide use.
- **Profit margins are negative across all three seasons** in this dataset, with Zaid performing worst — a notable finding worth further investigation into cost structure.
- **Disease/pest risk is highest in Kharif**, consistent with higher humidity and rainfall in that season.
- **Seasonal yield patterns are not consistent across states** — e.g., Punjab peaks in Rabi while most other states peak in Kharif - so planning should be state-specific rather than applying one national rule.

## Recommendations

- Prioritize irrigation efficiency (e.g., drip irrigation) over blanket increases in fertilizer/pesticide use
- Investigate the cost structure behind negative profit margins, especially in Zaid
- Target disease/pest management resources more heavily during Kharif
- Tailor seasonal planning by state rather than applying uniform national recommendations
- Collect multiple years of data to confirm whether seasonal yield trends hold over time

## How to Run

1. Clone this repository
2. Install dependencies:
   ```
   pip install pandas numpy matplotlib seaborn scipy jupyter
   ```
3. Launch Jupyter and open the notebook:
   ```
   jupyter notebook Seasonal_Agriculture_Performance_Analysis.ipynb
   ```
4. Run all cells to reproduce the full analysis and visualizations

## Author

Vishal Rajbhar
