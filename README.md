# Linear Regression - Advertising Sales

Predicting product sales from advertising budgets (TV, Radio, Newspaper) using **simple** and **multiple linear regression** with scikit-learn.

**Kaggle notebook:** [Linear Regression - Advertising Sales](https://www.kaggle.com/code/amrbakr95/linear-regression-advertising-sales)

## Dataset

`advertising.csv`: 200 rows, 4 numeric columns, no missing values or duplicates.

| Column | Meaning |
|---|---|
| `TV` | TV advertising budget (thousands of dollars) |
| `Radio` | Radio advertising budget (thousands of dollars) |
| `Newspaper` | Newspaper advertising budget (thousands of dollars) |
| `Sales` | Product sales (thousands of units), the target |

## Steps

1. **Exploration:** `info()`, `describe()`, missing values and duplicates check.
2. **Visualization:** scatter plot of each budget vs. Sales, and a correlation heatmap.
3. **Split:** 80% train / 20% test with `train_test_split(random_state=42)`.
4. **Simple linear regression:** `TV` only.
5. **Multiple linear regression:** `TV`, `Radio` and `Newspaper`.
6. **Evaluation:** MSE, RMSE, MAE and R² on the test set, plus an R² comparison chart.

## Key findings

- `TV` has the strongest correlation with `Sales` (0.90), `Radio` is weaker (0.35) and `Newspaper` is close to none (0.16).
- Adding `Radio` and `Newspaper` improved the model: R² went from **0.80** to **0.91**.
- The `Newspaper` coefficient is almost zero (0.004), so newspaper ads barely affect sales.

## Results

**Simple model:** `Sales = 7.007 + 0.0555 · TV`

**Multiple model:** `Sales = 4.714 + 0.0545 · TV + 0.1009 · Radio + 0.0043 · Newspaper`

| Model | Features | RMSE | MAE | R² |
|---|---|---|---|---|
| Simple | TV | 2.47 | 1.95 | 0.80 |
| Multiple | TV, Radio, Newspaper | 1.71 | - | 0.91 |

## How to run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

Open `linear-regression-advertising-sales.ipynb`. The notebook reads the data from the Kaggle input path; to run it locally, change the path in `pd.read_csv(...)` to `"advertising.csv"`.

## Tools

Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn
