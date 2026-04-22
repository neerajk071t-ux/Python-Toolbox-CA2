# 🛒 Retail Customer Segmentation Analysis

Exploratory Data Analysis and Predictive Modeling on 50,000 retail customers across Urban, Semi-Urban, and Rural regions.

---

## 📌 Project Overview

This project analyzes customer behavior to understand what drives spending, which segments are most valuable, and how region and payment preferences vary. The goal is to extract actionable insights from customer data using EDA, hypothesis testing, and regression modeling.

Key areas explored:
- Spending patterns across customer segments
- Relationship between income and monthly spend
- Region-wise customer distribution and payment preferences
- Statistical comparison of high-value vs occasional customers
- Predicting monthly spend using customer behavior features

---

## 📂 Dataset

**File:** `retail_customer_segmentation.csv`

| Column | Description |
|--------|-------------|
| customer_id | Unique customer ID |
| age | Customer age (18–70) |
| annual_income | Yearly income |
| months_active | How long the customer has been active |
| avg_monthly_spend | Average spend per month |
| purchase_frequency | How often they purchase |
| avg_order_value | Average value per order |
| discount_usage_rate | How often they use discounts (0–1) |
| return_rate | Product return rate |
| browsing_time_minutes | Time spent browsing per session |
| support_interactions | Number of support contacts |
| payment_method | Card / UPI / Wallet |
| region | Urban / Semi-Urban / Rural |
| customer_segment | Occasional / Regular / Loyal / High_Value |

- **50,000 records** · **14 columns** · Missing values handled via median imputation

---

## 🧹 Data Cleaning & Preprocessing

- Filled missing values in 7 numeric columns using median
- Created new features: `yearly_spend`, `age_group`, `high_discount_user`
- Defined age groups: Young (18–24), Adult (25–39), Middle-Aged (40–54), Senior (55+)

---

## ❓ Key Questions & Insights

### 1️⃣ How does spending vary across customer segments?
- Bar chart of average monthly spend per segment
- Boxplot of order value distribution by segment
- **Insight:** High_Value customers spend significantly more per month; Occasional customers have the most spread in order values

### 2️⃣ Does higher income lead to higher spending?
- Scatter plot of annual income vs monthly spend (colored by segment)
- Full correlation heatmap
- **Insight:** Weak-to-moderate correlation between income and spend — purchasing behavior is influenced by more than just income

### 3️⃣ How do region and payment method vary across customers?
- Bar chart of customer count by region
- Grouped bar chart of payment preference by region
- **Insight:** Urban regions dominate customer base; Card is the most used payment method across all regions

### 4️⃣ Do High_Value customers spend significantly more than Occasional customers? (Hypothesis Testing)
- Two-sample independent t-test
- **H₀:** No difference in monthly spend between High_Value and Occasional segments
- **H₁:** High_Value customers spend significantly more
- **Insight:** p-value < 0.05 → Reject H₀; the spending difference is statistically significant

### 5️⃣ Can we predict a customer's monthly spend? (Linear Regression)
- Features: Annual Income, Purchase Frequency, Browsing Time, Discount Usage, Months Active
- Target: Average Monthly Spend
- Metrics: R² Score, MAE
- **Insight:** Purchase frequency and browsing time are stronger predictors of spend than income alone

### 6️⃣ Which variables are most strongly related to spending behavior?
- Full correlation matrix heatmap
- Feature importance from regression coefficients
- Outlier detection boxplots for all key variables
- **Insight:** avg_order_value and purchase_frequency are most correlated with monthly spend; discount_usage_rate shows negative impact on order value

---

## 🛠️ Technologies Used

- Python · Pandas · NumPy · Matplotlib · Seaborn · Scikit-learn · SciPy

---

## 📂 File Structure

```
├── retail_customer_segmentation.csv
├── preprocessing_eda.py
├── objective1_spending_by_segment.py
├── objective2_income_vs_spend.py
├── objective3_region_payment.py
├── objective4_hypothesis.py
├── objective5_regression.py
├── objective6_correlation_importance.py
└── plots/
```

---

## ▶️ How to Run

```bash
pip install pandas matplotlib seaborn scikit-learn scipy
python preprocessing_eda.py
python objective1_spending_by_segment.py
# ... and so on
```

---

## 📈 Key Learnings

- Customer segment is a stronger indicator of spend than income
- High_Value customers are only 10.5% of total customers but statistically distinct in behavior
- Urban customers dominate but Rural customers are not far behind in average spend
- Discount usage negatively correlates with order value — discount-heavy buyers tend to spend less per order
- Purchase frequency is the most important feature for predicting monthly spend

---

## 👤 Author

**[Your Friend's Name]**
Python Toolbox Project · 2025
