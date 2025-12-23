# Copilot Instructions for Data Analysis Project

## Project Overview
This is a data analysis workspace containing two primary datasets:
- **AI Financial Market Data**: `ai_financial_market_daily_realistic_synthetic.csv` - Daily time series of R&D spending, AI revenue, and stock impacts across companies (10,961+ rows)
- **Amul Product Sales**: `amul_product_sales_2016_2025.csv` - Annual sales data by product SKU, category, and pricing (2016-2025)

Analysis is performed using Jupyter notebooks with pandas and visualization libraries.

## Critical Conventions & Patterns

### File Path Handling
**Pattern**: When constructing file paths in notebooks, **always use raw strings or forward slashes** to avoid escape sequence errors.
```python
# ✓ CORRECT - Raw string
df = pd.read_csv(r'C:\Users\Admin\Documents\GitHub\Data\ai_financial_market_daily_realistic_synthetic.csv')

# ✓ CORRECT - Forward slashes (cross-platform)
df = pd.read_csv('C:/Users/Admin/Documents/GitHub/Data/ai_financial_market_daily_realistic_synthetic.csv')

# ✗ WRONG - Backslashes cause Unicode escape errors
df = pd.read_csv('C:\Users\Admin\Documents\GitHub\Data\ai_financial_market_daily_realistic_synthetic.csv')
```

### Data Schema Context
- **Financial Market Data**: Contains Date, Company, R&D_Spending_USD_Mn, AI_Revenue_USD_Mn, AI_Revenue_Growth_%, Event, Stock_Impact_%
- **Amul Sales Data**: Contains Year, SKU, Product, Category, Price_INR, Units_Sold
- Parse dates when loading financial data for time-series analysis

## Workflow Patterns
1. **Loading**: Use `pd.read_csv()` with proper path handling and `parse_dates` parameter for temporal data
2. **Exploration**: Check shape, dtypes, null values before analysis
3. **Visualization**: Use plotly or matplotlib for interactive/static plots respectively
4. **Analysis**: Perform aggregations, groupby operations, and statistical analysis on clean data

## Key Files
- CSV datasets stored in workspace root directory
- Notebooks stored in workspace (currently: `Untitled-1.ipynb`)
