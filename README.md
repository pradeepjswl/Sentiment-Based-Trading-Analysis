
# Market Sentiment & Trader Behavior Analysis

## 📂 Project Overview
This project investigates the relationship between **institutional trading behavior** and **crypto market sentiment**. By analyzing high-frequency trading data against the **Bitcoin Fear & Greed Index**, this study aims to identify "Smart Money" patterns, quantify behavioral edges, and propose automated trading strategies.

The analysis focuses on four key pillars:
1.  **Profitability:** Efficiency (Profit Factor) across sentiment regimes.
2.  **Risk:** Drawdown analysis and PnL distribution (Tail Risk).
3.  **Volume:** Liquidity provision relative to market panic/euphoria.
4.  **Behavior:** Directional bias (Long vs. Short) shifts.

---

## 📂 Directory Structure
This repository adheres to the strict assignment format:

ds_/
├── notebook_1.ipynb        # Main analysis code (Data Processing, EDA, Visuals)
├── notebooks/              # (Optional) Sandbox notebooks
├── csv_files/              # Data Storage
│   ├── historical_data.csv # Raw Trader Data
│   ├── fear_greed_index.csv# Raw Sentiment Data
│   ├── merged_data.csv     # Processed Dataset
│   └── daily_stats.csv     # Aggregated Daily Metrics
├── outputs/                # Generated Visualizations
│   ├── performance_alpha.png
│   ├── risk_drawdown.png
│   ├── strategic_bias.png
│   └── ... (All other charts)
├── ds_report.pdf           # Final Business-Ready Research Report
└── README.md               # Project 

---

## 🛠️ Setup & Installation

To replicate this analysis, ensure you have the following Python libraries installed:

pip install pandas numpy matplotlib seaborn

### **How to Run**

1.  **Clone/Download** this repository.
2.  Ensure raw data files (`historical_data.csv` and `fear_greed_index.csv`) are placed in the root directory or uploaded to your Google Colab session.
3.  Open **`notebook_1.ipynb`**.
4.  Run all cells to generate the processed CSVs in `csv_files/` and charts in `outputs/`.

## Collab Link: https://colab.research.google.com/drive/17hKZ4cprRmNRVGff67byau9G5tPdEhYj?usp=sharing
-----

## 📊 Methodology

### 1 Data Processing

  * **Time Synchronization:** All timestamps converted to UTC and normalized to daily resolution.
  * **Merging:** Inner join performed on `Date` to align trade execution with daily sentiment values.
  * **Feature Engineering:**
      * `Profit Factor`: Gross Win / Gross Loss.
      * `Win Rate`: Percentage of profitable trades.
      * `Sentiment Class`: Categorization (Extreme Fear, Fear, Neutral, Greed, Extreme Greed).

### 2 Analytical Approach

  * **Regime Analysis:** Segmenting performance metrics by sentiment class.
  * **Rolling Metrics:** Calculating 50-trade rolling win rates to detect alpha decay.
  * **Session Profiling:** Aggregating PnL by hour of day (0-24 UTC).

-----

## 💡 Key Findings

1.  **Contrarian Alpha:** The strategy effectively "Fades the Herd."
      * **Buying Panic:** Net Long Bias (\>60%) when Sentiment \< 25.
      * **Shorting Euphoria:** Net Short Bias when Sentiment \> 75.
2.  **Peak Efficiency:** The strategy is most profitable during **Extreme Greed**, achieving a **Profit Factor of 11.0x**.
3.  **Liquidity Provision:** Volume is highest during **Fear**, indicating the trader provides liquidity when the market is crashing.
4.  **The "Golden Hour":** Profitability peaks between **12:00 UTC and 14:00 UTC**, coinciding with the London/New York session overlap.

-----

## 📉 Visualizations Included

The `outputs/` folder contains high-resolution charts used in the final report:

  * **`performance_alpha.png`**: Profit Factor & Win Rate by Sentiment.
  * **`strategic_bias.png`**: Long/Short ratio changes across regimes.
  * **`risk_drawdown.png`**: Equity curve and max drawdown visualization.
  * **`pattern_regime_overlay.png`**: Cumulative PnL plotted against sentiment background zones.
  * **`hourly_pnl.png`**: Profitability heatmap by hour of day.
and many others.


