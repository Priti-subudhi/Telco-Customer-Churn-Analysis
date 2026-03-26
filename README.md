# 📊 Telco Customer Churn Analysis

An exploratory data analysis (EDA) project on a Telco customer dataset to identify the key drivers of customer churn and surface actionable retention insights.

---

## 📁 Repository Structure

```
├── Customer Churn.csv                    # Raw dataset (7,043 records)
├── Telco_customer_churn.ipynb            # Jupyter notebook with full EDA
├── Telco_Churn_Executive_Summary.docx    # Executive summary report
└── README.md                             # This file
```

---

## 📌 Project Overview

**Goal:** Identify patterns and drivers of customer churn using visualisation and statistical analysis.

**Dataset:** IBM Telco Customer Churn dataset  
**Records:** 7,043 customers | **Features:** 21 columns  
**Churn Rate:** 26.54% (1,869 churned out of 7,043 customers)

---

## 🛠️ Tools & Libraries

| Tool | Purpose |
|------|---------|
| Python 3 | Core programming language |
| pandas | Data loading, cleaning, manipulation |
| NumPy | Numerical operations |
| Matplotlib | Base visualisations |
| Seaborn | Statistical charts and countplots |
| Jupyter Notebook | Interactive analysis environment |

---

## 🧹 Data Preprocessing

| Step | Detail |
|------|--------|
| Missing values | 11 blank entries in `TotalCharges` (all with `tenure = 0`) replaced with `0` |
| Type casting | `TotalCharges` converted from object → float |
| Encoding | `SeniorCitizen` recoded from binary (`0`/`1`) to categorical (`No`/`Yes`) |
| Duplicates | Confirmed 0 duplicate `customerID` entries |
| Null check | 0 null values across all 21 columns after preprocessing |

---

## 📊 Key Findings

### Overall Churn
| Metric | Value |
|--------|-------|
| Total customers | 7,043 |
| Churned | 1,869 (26.54%) |
| Retained | 5,174 (73.46%) |

---

### 1. Contract Type — Strongest Churn Predictor
Month-to-month subscribers churn at a rate approximately **14x higher** than two-year contract holders.

| Contract Type | Approx. Customers | Churn Rate |
|---------------|-------------------|------------|
| Month-to-Month | ~3,875 | ~42% |
| One Year | ~1,473 | ~11% |
| Two Year | ~1,695 | ~3% |

---

### 2. Tenure — Early Lifecycle Risk
- Customers with **1–2 months** of tenure show the highest churn concentration
- Customers with **3+ years (36+ months)** are significantly more loyal
- Average tenure: **32.4 months** | Median: **29 months** | Range: 0–72 months

---

### 3. Senior Citizens
- Senior citizens represent **~16.2%** of the customer base (≈1,142 customers)
- Churn rate among seniors: **~41.7%** vs **~23.6%** for non-seniors

---

### 4. Payment Method
| Payment Method | Churn Risk |
|----------------|-----------|
| Electronic check | Highest |
| Mailed check | Moderate |
| Bank transfer (auto) | Lower |
| Credit card (auto) | Lowest |

---

### 5. Internet Service Type
| Service Type | Churn Risk |
|-------------|-----------|
| Fiber optic | High |
| DSL | Moderate |
| No internet service | Low |

---

### 6. Value-Added Services
Customers **without** the following services churned at notably higher rates:

| Service | Impact if Absent |
|---------|-----------------|
| Online Security | Very High |
| Tech Support | Very High |
| Online Backup | High |
| Device Protection | High |

---

### 7. Gender
Churn rates are **roughly equal** across male and female customers (~50/50 dataset split). Gender is not a significant standalone predictor.

---

## 📈 Charts Produced

The notebook contains the following visualisations:

1. **Count of Customers by Churn** — Bar chart (No: 5,174 | Yes: 1,869)
2. **Percentage of Churned Customers** — Pie chart (73.46% vs 26.54%)
3. **Churn by Gender** — Countplot with hue
4. **Churn by Senior Citizen** — Countplot + stacked percentage bar chart
5. **Tenure Distribution by Churn** — Histogram (72 bins)
6. **Churn by Contract Type** — Countplot with hue
7. **Service Usage vs Churn** — 3×3 subplot grid (PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies)
8. **Churn by Payment Method** — Countplot with hue

---

## 💡 Strategic Recommendations

1. **Convert month-to-month customers** to annual or two-year contracts through incentives — highest-impact retention lever
2. **Early-lifecycle intervention** (months 1–3): onboarding calls, guided setup, service orientation
3. **Bundle online security and tech support** as default inclusions or low-cost add-ons
4. **Investigate fiber optic pricing** — fiber customers churn significantly more than DSL customers
5. **Promote auto-pay enrollment** — move electronic check users to bank transfer or credit card
6. **Senior citizen retention program** — specialised support and simplified plans for the ~16.2% senior segment with ~41.7% churn rate

---

## 📋 Dataset Summary Statistics

| Feature | Min | Mean | Median | Max | Std Dev |
|---------|-----|------|--------|-----|---------|
| Tenure (months) | 0 | 32.4 | 29 | 72 | 24.56 |
| Monthly Charges ($) | 18.25 | 64.76 | 70.35 | 118.75 | 30.09 |
| Total Charges ($) | 0 | 2,279.73 | 1,394.55 | 8,684.80 | 2,266.79 |

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/telco-churn-analysis.git
   cd telco-churn-analysis
   ```

2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. Launch the notebook:
   ```bash
   jupyter notebook Telco_customer_churn.ipynb
   ```

---

## 📄 Report

A detailed executive summary with full findings, tables, and recommendations is available in:
**`Telco_Churn_Executive_Summary.docx`**

---

*Analysis performed using Python · Dataset: IBM Telco Customer Churn Sample*

