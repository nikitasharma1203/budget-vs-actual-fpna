# Budget vs Actual & Forecasting Analysis (FP&A)

# **ON A BREAK**

This project has a real-world **Financial Planning & Analysis (FP&A)** workflow by forecasting demand, creating budgets, and analyzing performance variances using historical industrial production data.

Applied forecasting techniquesn **Linear Regression** and **ARIMA** are used to:
- Forecast future demand
- Translate forecasts into budget assumptions
- Compare actual performance against budget
- Identify and explain variance drivers

Since company-level revenue data is not publicly available, **industrial production indices are used as a proxy for demand/volume**, which is a standard approach in macro-level FP&A and demand planning.

---

1. What do we expect performance to be? *(Forecasting)*
2. What did we plan for? *(Budgeting)*
3. Why did we over- or under-perform? *(Variance analysis)*

---
Seasonality & Trend Analysis
- Analyzed long-term demand trends
- Identified recurring monthly seasonality patterns

**Insight:**  
Seasonality reinforces the need for monthly-level budgeting and continuous performance monitoring.

---

### Forecasting Models

#### Linear Regression (ML Perspective)
- Predictor: Time index
- Strength: Captures long-term structural growth
- Best suited for: Strategic planning and budgeting

#### ARIMA (Statistical Time-Series Model)
- Captures short-term temporal dependencies
- Produces more conservative forecasts
- Best suited for: Short-term monitoring and control

Time-aware train-test splits were used to avoid data leakage.

---

### 4. Forecast Evaluation
Models were evaluated using:
- **MAE (Mean Absolute Error)**
- **RMSE (Root Mean Squared Error)**

This enables objective model comparison for planning use cases.

---

### 5. Budget Creation
A budget was constructed using a prior-year actuals approach:

Budget(t) = Actual(t−12) × (1 + Growth Rate)

- Annual growth assumption: **8%**
- Assumptions were explicitly stated and consistently applied

This mirrors standard FP&A budgeting practices.

---

### 6. Budget vs Actual Analysis
- Calculated absolute and percentage variances
- Visualized actual vs budget performance over time

**Observation:**  
The budget tracks long-term growth well, while short-term deviations highlight demand volatility rather than budgeting errors.

---

### 7. Variance Driver Analysis
To explain *why* variance occurred, key categories were analyzed as drivers:
- Consumer Durables
- Consumer Non-Durables
- Capital Goods
- Intermediate Goods


Consumer durables exhibit the strongest relationship with budget variance, indicating demand cyclicality as the primary driver.

---

- Growth-based budgets are effective for strategic planning
- Monthly variance is largely demand-driven, not assumption failure
- Linear regression supports long-term planning
- ARIMA enhances short-term forecast control
- Combining models improves FP&A decision support

