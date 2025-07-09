# 🧠 Customer Personality Analysis – Python Case Study

This project performs a comprehensive analysis of customer demographics, product spending behavior, and engagement to generate actionable insights for targeted marketing strategies.

---

## 📁 Dataset

- **Source**: Internal (CSV file provided)
- **File**: `marketing_data.csv`
- **Records**: 2,240 customers
- **Features**: Income, Spending on Products (Wine, Meat, Fish, etc.), Customer Since, and more

---

## 🎯 Objective

To help the company better understand its customer base by analyzing their income levels, spending behaviors, and enrollment patterns.

---

## 📊 Questions Answered

### ✅ Q1: How many customers have income above 50,000?

**Code**:
```python
high_income_customers = df[df['Income'] > 50000]
print("Number of customers with income > 50000:", high_income_customers.shape[0])
```

**Conclusion**:
> There are 1,252 customers with income > ₹50,000 — a premium segment ideal for targeted campaigns.

---

### ✅ Q2: How much money was spent on wine and what percentage is it of total spend?

**Code**:
```python
total_wine = df['MntWines'].sum()
total_all = df['total_spent'].sum()
wine_pct = (total_wine / total_all) * 100
```

**Conclusion**:
> Wine contributes ~31% of total spending — the most dominant product category.

---

### ✅ Q3: In which year is the maximum amount spent by customers?

**Code**:
```python
df['Year'] = pd.to_datetime(df['Dt_Customer']).dt.year
df.groupby('Year')['total_spent'].sum().sort_values(ascending=False)
```

**Conclusion**:
> Customers acquired in 2013 spent the most — revisit strategies from that year.

---

### ✅ Q4: Which month has the highest average income and who are the top 10 customers?

**Code**:
```python
df['Month'] = pd.to_datetime(df['Dt_Customer']).dt.month
top_customers = df[df['Month'] == df.groupby('Month')['Income'].mean().idxmax()]
```

**Conclusion**:
> October had the highest average income. Best month to push premium offers.

---

### ✅ Q5: Total spent on each product and its % share

**Code**:
```python
totals = df[categories].sum()
totals_pct = (totals / totals.sum()) * 100
```

**Conclusion**:
> Wine and Meat dominate spending. Fruit, Sweets underperform — improve marketing here.

---

### ✅ Q6: Total amount spent per weekday and its percentage

**Code**:
```python
df['Weekday'] = pd.to_datetime(df['Dt_Customer']).dt.day_name()
weekday_spent = df.groupby('Weekday')['total_spent'].sum()
```

**Conclusion**:
> Monday and Friday have peak spending. Ideal for running offers or email campaigns.

---

## 📈 Tools & Skills Used

- Python (Pandas, Matplotlib, Seaborn)
- Data Cleaning & Transformation
- Aggregation, Grouping, Feature Engineering
- Visualizations & Insight Extraction

---

## 📌 How to Run

1. Clone the repository:
```bash
git clone https://github.com/your-username/customer-personality-analysis-python.git
```

2. Open in Jupyter and run:
```bash
Customer_Personality_Analysis.ipynb
```

---

## 👨‍💻 Author

**Muhammed Saheer K**  
[Portfolio Website](https://muhammed-saheer.github.io/muhammedsaheer.github.io/)  
[LinkedIn](https://www.linkedin.com/in/muhammed-saheer-k-34a7372a8/)  
[GitHub](https://github.com/muhammed-saheer)
