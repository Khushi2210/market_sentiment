# Trader Performance vs Market Sentiment Analysis

Analysis of how cryptocurrency traders perform and behave under different market sentiment conditions (Fear vs Greed) using Hyperliquid trading data.

## Project Overview

This project analyzes the relationship between Bitcoin market sentiment (Fear/Greed Index) and trader behavior/performance on Hyperliquid. The goal is to identify patterns that could inform better trading strategies.

## Data Sources

1. **Bitcoin Fear & Greed Index** - Market sentiment classification by date
2. **Hyperliquid Historical Trader Data** - Trading activity including positions, PnL, leverage, etc.

## Setup Instructions

### Requirements

```bash
pip install -r requirements.txt
```

### Running the Analysis

1. **Place the data files** in the project directory:
   - `bitcoin_fear_greed.csv`
   - `historical_trader_data.csv`

2. **Run the Jupyter notebook**:
   ```bash
   jupyter notebook analysis.ipynb
   ```
   
3. **Launch the dashboard** (after running the notebook):
   ```bash
   streamlit run streamlit_app.py
   ```

## Project Structure

```
.
├── analysis.ipynb              # Main analysis notebook
├── streamlit_app.py           # Interactive dashboard
├── requirements.txt           # Python dependencies
├── README.md                  # This file
├── outputs/                   # Generated charts and analysis
│   ├── pnl_comparison.png
│   ├── behavior_comparison.png
│   ├── segment_analysis.png
│   └── cluster_visualization.png
└── processed_data/            # Processed datasets (generated)
    ├── processed_daily_data.csv
    └── trader_profiles.csv
```

## Analysis Components

### Part A: Data Preparation
- Data loading and validation
- Missing value and duplicate checking
- Timestamp alignment and daily aggregation
- Key metrics calculation (PnL, win rate, leverage, trade frequency, long/short ratio)

### Part B: Analysis
- **Performance comparison**: Fear vs Greed days analysis
- **Behavioral analysis**: How traders adjust strategy based on sentiment
- **Segmentation**: 
  - High vs Low leverage traders
  - Frequent vs Infrequent traders
  - Consistent vs Inconsistent performers

### Part C: Actionable Strategies
Based on the analysis, two main strategy recommendations:

1. **Leverage Management Strategy**: Reduce leverage during Fear periods, especially for high-leverage traders
2. **Trading Frequency Strategy**: Reduce overtrading during Fear periods

### Bonus Features
- **Clustering Analysis**: K-Means clustering to identify trader archetypes
- **Interactive Dashboard**: Streamlit app for exploring results dynamically

## Key Findings

1. Trader performance (PnL and win rate) shows significant differences between Fear and Greed market conditions
2. Behavioral metrics (trade frequency, leverage, position sizing) shift based on sentiment
3. Different trader segments respond uniquely to market sentiment changes
4. High-leverage traders tend to underperform during Fear periods
5. Overtrading during Fear periods correlates with worse outcomes

## Visualizations

The analysis generates several charts:
- PnL distribution comparisons
- Win rate box plots
- Behavioral metric comparisons
- Segment performance analysis
- Trader clustering visualizations

## Technologies Used

- **Python 3.8+**
- **pandas** - Data manipulation
- **numpy** - Numerical operations
- **matplotlib/seaborn** - Static visualizations
- **plotly** - Interactive charts
- **scikit-learn** - Clustering and ML
- **scipy** - Statistical testing
- **streamlit** - Dashboard framework
