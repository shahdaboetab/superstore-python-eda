# Superstore Sales: Exploratory & Statistical Analysis (Python)

Exploratory and statistical analysis of 9,993 Superstore order lines (2014-2017) in Python.
Built for the **UneeQ Interns** Data Analysis program (Python EDA task).

## Business questions
1. How do sales and profit evolve, and is there seasonality?
2. Which sub-categories make or lose money?
3. How do discounts affect profit?
4. Do segments and regions differ in profitability? (statistical tests)
5. Which customers matter most, and who is at risk or loses money?

## Dataset
[Superstore Sales (Kaggle)](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final): 21 columns, US orders, 2014-2017.

## Files
| File | Description |
|---|---|
| `superstore_eda.ipynb` | Full notebook with outputs (open on GitHub to read it) |
| `superstore_eda.html` | Same notebook as a web page |
| `charts/` | 6 charts exported from the notebook |
| `Sample - Superstore.csv` | Source data |

## Approach
1. **Inspect:** shape, types, blanks, duplicates, summary statistics.
2. **Clean (all logged in the notebook):** 1 duplicate line removed (ignoring Row ID), 16 cells trimmed, dates converted, 449 postal codes zero-padded, 32 Product IDs with several names standardised, helper columns added. Loss-making lines are kept and flagged.
3. **Outliers:** IQR rule; kept because they are real transactions.
4. **Analysis:** trend and seasonality, sub-category profit, discount impact, regional and segment comparison.
5. **Statistical tests:** Welch t-test, Mann-Whitney U, ANOVA, Kruskal-Wallis, Spearman correlation (rank-based tests used because profit is strongly skewed).
6. **Segmentation:** RFM scoring of 793 customers.

## Key findings
- Sales **$2.30M**, profit **$286K**, margin **12.5%**; sales grew **51.5%** from 2014 to 2017.
- **Sep, Nov and Dec bring 42.9%** of sales (Nov + Dec alone 29.5%).
- **Furniture earns only 2.5%** margin (Technology 17.4%, Office Supplies 17.0%); Tables, Bookcases and Supplies lose money.
- **Discounts above 20% lose money** on 97% of 1,392 lines, a combined **-$135K**. Mean profit per line is -$97 versus +$49 at 20% or less (p < 0.001).
- Consumer and Corporate earn **similar profit per line** (no significant difference).
- **Central** has the weakest margin (7.9%): its average discount is 24%, 27.7% of its lines are discounted above 20% (West: 3.7%), and 31.9% of its lines lose money (West: 9.9%).
- 193 **Champions** (RFM) generate 40% of sales; some of the biggest accounts lose money.

## How to run
```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
jupyter notebook superstore_eda.ipynb      # keep the CSV in the same folder
```

## Assumptions and limitations
No cost or returns data; correlation is not causation; US data only; product names standardised per Product ID.

## Video walkthrough
[Watch here](PUT-LINK-HERE)

## Author
Shahd Aboetab | [LinkedIn](https://linkedin.com/in/shahdaboetab)
