# KIZ BAŞINA EĞİTİMİ ÖDEVLERİ

# Final Case 1

# ✈️ Airline Passenger Satisfaction Analysis

## 📌 Project Objective

The goal of this project is to conduct an end-to-end **exploratory data analysis (EDA)** using the **Airline Passenger Satisfaction Dataset**. The project focuses on:

- Understanding the dataset through statistical summaries  
- Handling missing values  
- Identifying and treating outliers  
- Visualizing relationships in the data  
- Reporting insights clearly and effectively  

---

## 📂 Dataset Overview

We are using the **Airline Passenger Satisfaction Dataset**, which contains data collected from airline passengers including:

- Demographic attributes  
- Flight experience factors (e.g., seat comfort, service, delays)  
- A target variable: **Satisfaction (Satisfied / Neutral or Dissatisfied)**

Key columns include:

- `Gender`, `Age`, `Customer Type`, `Type of Travel`, `Class`
- `Flight Distance`, `Inflight wifi service`, `Arrival Delay in Minutes`, etc.
- `satisfaction`: Target variable (binary)

---

## 📊 Statistical Summary

A statistical overview of numerical features provides insights into the central tendency and dispersion:

```python
df.describe()
This includes:

Mean, median (50%), standard deviation

Minimum and maximum values

Count of non-null values

These statistics help us understand data distribution and detect potential anomalies.

🔍 Missing Value Analysis
To identify missing values, we used:

python
Kopyala
Düzenle
missing_count = df.isnull().sum()
missing_percent = (missing_count / len(df)) * 100

missing_data = pd.DataFrame({
    "Missing Count": missing_count,
    "Missing Percentage (%)": missing_percent
}).sort_values(by="Missing Percentage (%)", ascending=False)

missing_data = missing_data[missing_data["Missing Count"] > 0]
Findings:

Only Arrival Delay in Minutes had missing values.

We handled this by either:

Filling with the median value (robust against outliers), or

Removing rows with nulls (if a small number)

---

## ⚠️ Outlier Detection
We used IQR (Interquartile Range) method to detect outliers:

python
Kopyala
Düzenle
def detect_outliers_iqr(data, column):
    Q1 = data[column].quantile(0.25)
    Q3 = data[column].quantile(0.75)
    IQR = Q3 - Q1
    lower_bound = Q1 - 1.5 * IQR
    upper_bound = Q3 + 1.5 * IQR
    return data[(data[column] < lower_bound) | (data[column] > upper_bound)]
Outlier analysis was done for:

Flight Distance

Departure Delay in Minutes

Arrival Delay in Minutes

Visualized with:

python
Kopyala
Düzenle
sns.boxplot(data=df[["Flight Distance", "Departure Delay in Minutes", "Arrival Delay in Minutes"]])
📈 Data Visualization
We used appropriate visualizations to explore both numerical and categorical variables:

1. Categorical Variables (Countplot)
python
Kopyala
Düzenle
sns.countplot(data=df, x='satisfaction', hue='Class', palette='Set2')
2. Numerical Variables (Histogram)
python
Kopyala
Düzenle
for col in numeric_cols:
    sns.histplot(df[col], kde=True, bins=30)
3. Correlation Heatmap
python
Kopyala
Düzenle
sns.heatmap(df.corr(numeric_only=True), annot=True, cmap='coolwarm')
These visualizations helped us understand:

Distribution of delay times

Relationship between flight class and satisfaction

Correlations between features

⚠️ About the FutureWarning in Seaborn
When using Seaborn's countplot(), you might see:

swift
Kopyala
Düzenle
FutureWarning: Passing `palette` without assigning `hue` is deprecated...
This is not an error — it's a warning for upcoming versions. It means that using palette alone without hue will not be supported in the future. You can ignore it safely, or follow Seaborn’s suggestion:

python
Kopyala
Düzenle
sns.countplot(data=df, x='satisfaction', hue='satisfaction', palette='Set2', legend=False)
✅ Conclusion
This project demonstrated essential steps in data analysis, including:

Loading and exploring the dataset

Summarizing key metrics

Handling missing values

Detecting and interpreting outliers

Producing useful visual insights

The analysis helps understand factors affecting passenger satisfaction and prepares the ground for future machine learning applications like classification models.

## 📎 Tools Used
Python (Pandas, NumPy, Seaborn, Matplotlib)

Google Colab for interactive development

GitHub for version control and submission

## 📌 Author
Eda Özge Uğurlu
