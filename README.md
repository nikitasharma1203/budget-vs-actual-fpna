# Budget vs Actual & Forecasting Analysis (FP&A)

## Summary
This project has a real-world **Financial Planning & Analysis (FP&A)** workflow by forecasting demand, creating budgets, and analyzing performance variances using historical industrial production data.

Applied forecasting techniquesn **Linear Regression** and **ARIMA** are used to:
- Forecast future demand
- Translate forecasts into budget assumptions
- Compare actual performance against budget
- Identify and explain variance drivers

Since company-level revenue data is not publicly available, **industrial production indices are used as a proxy for demand/volume**, which is a standard approach in macro-level FP&A and demand planning.

---

## Business Problem
FP&A teams repeatedly answer three critical questions:
1. What do we expect performance to be? *(Forecasting)*
2. What did we plan for? *(Budgeting)*
3. Why did we over- or under-perform? *(Variance analysis)*

---

## Dataset
**Use-Based Monthly Indices of Industrial Production (IIP)**  
- Frequency: Monthly  
- Time span: ~8+ years  
- Data type: Index-based production volumes  

### Key Categories
- Consumer Goods (Total) *(primary demand proxy)*
- Consumer Durables
- Consumer Non-Durables
- Capital Goods
- Basic Goods
- Intermediate Goods

> Revenue = Price × Volume  
> This project focuses on the **volume side**, which is often the primary driver of forecasting uncertainty.

---

## Methodology

### 1. Data Preparation
- Standardized inconsistent month formats 
- Converted month column to a datetime index
- Structured data for time-series forecasting

---

### 2. Seasonality & Trend Analysis
- Analyzed long-term demand trends
- Identified recurring monthly seasonality patterns

**Insight:**  
Seasonality reinforces the need for monthly-level budgeting and continuous performance monitoring.

---

### 3. Forecasting Models

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

Techniques used:
- Feature standardization
- Correlation analysis
- Regression-based attribution

**Key Finding:**  
Consumer durables exhibit the strongest relationship with budget variance, indicating demand cyclicality as the primary driver.

---

## Key Insights
- Growth-based budgets are effective for strategic planning
- Monthly variance is largely demand-driven, not assumption failure
- Linear regression supports long-term planning
- ARIMA enhances short-term forecast control
- Combining models improves FP&A decision support

---

## Tools
- Python
- Pandas, NumPy
- Scikit-learn
- Statsmodels
- Matplotlib

---

## Business Relevance
This project mirrors real FP&A activities including:
- Demand forecasting
- Budget formulation
- Performance variance tracking
- Driver-based business explanation

It demonstrates both **technical forecasting skills** and **finance-oriented analytical thinking**.

---

## Conclusion
> The budget accurately reflects long-term demand growth, while short-term variances are driven primarily by consumer durables volatility. Regression models support strategic planning, and ARIMA enhances short-term forecast control.
