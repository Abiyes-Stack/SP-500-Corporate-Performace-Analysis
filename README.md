# S&P 500 Corporate Performance Intelligence Report

A multi-factor analysis of 503 S&P 500 companies across operational efficiency, financial health, and market valuation — built to answer one question:

**Which sectors and companies run the most efficient operations, which are financially healthy, and where does market valuation not match fundamentals?**

## Key Findings

- **Energy** leads all sectors in operational efficiency (0.47 avg) with 67% of scored companies classified as Stars, yet remains the most undervalued sector by market multiples.
- **Strong-tier** companies carry 0.78 debt-to-equity vs. 5.25 for Distressed — a 6.7x leverage gap that is the clearest predictor of overall company quality in this dataset.
- **CF Industries, Texas Instruments, and APA Corporation** rank as the top three companies across all scoring dimensions — strong operations, healthy balance sheets, and undervalued by the market.
- **29 companies flagged** for unsustainable dividend payouts (>100%), with 15 being REITs where high payouts are structurally required by law.

## Scoring Models

| Model | Components | Weights | Coverage |
|-------|-----------|---------|----------|
| Efficiency Index | Operating Margin, EBITDA/Market Cap, Net Profit Margin | 40/30/30 | 419 companies (83%) |
| Health Score | ROE + ROA, Current + Quick Ratio, Debt-to-Equity (inverted) | 40/30/30 | 342 companies (68%) |
| Valuation Gap | Normalized Market Valuation − Normalized Fundamental Score | — | 421 companies (84%) |

## Classifications

**Growth vs. Efficiency Quadrants:** Star (121) · Cash Cow (89) · Turnaround Candidate (86) · Underperformer (123)

**Financial Risk Tiers:** Strong (86) · Stable (85) · Watch (85) · Distressed (86)

## Interactive Dashboard

[View on Tableau Public →](https://public.tableau.com/authoring/SP500CorporatePerformanceIntelligenceDashboard/SP500CorporatePerformanceIntelligenceDashboard#1)

## Project Structure

```
├── SP500_Corporate_Performance_Intelligence.ipynb   # Full analysis notebook (Phases 1-5)
├── sp500_master_dataset_final.csv                   # Cleaned dataset (503 × 106)
├── SP500_Executive_Summary.pdf                      # Executive summary
├── SP500_Executive_Summary.docx                     # Executive summary (Word)
├── visualizations/
│   ├── 01_sector_efficiency.png
│   ├── 02_quadrant_matrix.png
│   ├── 03_risk_tiers.png
│   ├── 04_valuation_gap.png
│   ├── 05_sector_dashboard.png
│   └── 06_combined_scorecard.png
└── README.md
```

## Data Sources

| Source | Records | Features | Role |
|--------|---------|----------|------|
| [S&P 500 Constituents](https://github.com/datasets/s-and-p-500-companies) (GitHub) | 503 | 3 | Dimension table (Symbol, Name, Sub-Industry) |
| [S&P 500 Financials](https://github.com/datasets/s-and-p-500-companies) (GitHub) | 503 | 14 | Market valuation metrics |
| [S&P 500 Company Descriptions](https://www.kaggle.com/) (Kaggle) | 496 | 73 | Operational & financial performance |

## Data Pipeline

- 72 string columns converted to numeric (B/M/K suffix parsing, percentage conversion, null handling)
- 127 GICS sub-industries mapped to 11 standard sectors
- Three-table join on ticker symbol (INNER + LEFT)
- 6 engineered features built from raw metrics
- Final dataset: 503 companies × 106 features

## Tools

Python · pandas · NumPy · matplotlib · seaborn · Google Colab · Tableau Public

## Author

**Samuel Manson**
