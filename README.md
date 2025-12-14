# indian-economy-key-indicators-
a beginner project to understand key indicators of indian economy
indian-economic-indicators/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   └── exploratory_analysis.ipynb
│
├── src/
│   ├── __init__.py
│   ├── fetch_data.py
│   ├── indicators.py
│   ├── visualization.py
│   └── utils.py
│
├── tests/
│   └── test_indicators.py
│
├── requirements.txt
├── README.md
├── .gitignore
└── main.py
pandas
numpy
matplotlib
seaborn
requests
jupyter
# Indian Economic Indicators 📈

This repository provides tools to collect, analyze, and visualize key indicators of the Indian economy.

## Indicators Included
- GDP Growth
- Inflation (CPI/WPI)
- Unemployment Rate
- Fiscal Deficit
- Trade Balance
- Forex Reserves
- Interest Rates
- Industrial Production (IIP)

## Data Sources
- RBI
- MOSPI
- World Bank
- IMF (optional)

## Usage
```bash
pip install -r requirements.txt
python main.py

---

## 📄 `src/fetch_data.py`
```python
import pandas as pd

def load_sample_data():
    """Load sample economic indicators (placeholder)."""
    data = {
        "Year": [2019, 2020, 2021, 2022, 2023],
        "GDP_Growth_%": [4.0, -7.3, 9.1, 7.2, 6.7],
        "Inflation_%": [3.7, 6.6, 5.1, 6.7, 5.4],
        "Unemployment_%": [5.3, 8.0, 6.2, 5.8, 5.4]
    }
    return pd.DataFrame(data)
def average_growth(df):
    return df["GDP_Growth_%"].mean()

def highest_inflation(df):
    return df["Inflation_%"].max()

def unemployment_trend(df):
    return df[["Year", "Unemployment_%"]]
import matplotlib.pyplot as plt
import seaborn as sns

def plot_gdp_growth(df):
    sns.lineplot(x="Year", y="GDP_Growth_%", data=df)
    plt.title("India GDP Growth Rate")
    plt.show()

def plot_inflation(df):
    sns.barplot(x="Year", y="Inflation_%", data=df)
    plt.title("Inflation Rate in India")
    plt.show()
from src.fetch_data import load_sample_data
from src.indicators import average_growth, highest_inflation
from src.visualization import plot_gdp_growth, plot_inflation

def main():
    df = load_sample_data()
    
    print("Average GDP Growth:", average_growth(df))
    print("Highest Inflation:", highest_inflation(df))
    
    plot_gdp_growth(df)
    plot_inflation(df)

if __name__ == "__main__":
    main()
__pycache__/
.ipynb_checkpoints/
.env
*.csv
