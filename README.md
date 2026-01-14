# Credit Risk Analysis & Expected Credit Loss (ECL) Modeling

A comprehensive machine learning framework for credit risk assessment, calculating Expected Credit Loss through PD (Probability of Default), LGD (Loss Given Default), and EAD (Exposure at Default) modeling on consumer loan data.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Status](https://img.shields.io/badge/Status-Complete-success)

---

## 📊 Project Overview

This project implements a **Basel III-compliant credit risk framework** to assess loan default risk and calculate expected credit losses for a consumer loan portfolio. The system analyzes 2,000+ loan records and calculates ECL for a $11M portfolio using machine learning techniques.

### Key Results
- **Total Expected Credit Loss:** $649K (10.9% of portfolio)
- **Portfolio Analyzed:** 600 loans worth $11M
- **Risk Segmentation:** Identified 2.2% high-risk loans driving 3.4% of losses
- **Best Model:** XGBoost + SMOTE

---

## 🎯 Features

- **End-to-End ECL Framework:** PD, LGD, and EAD modeling
- **Multiple ML Models:** Logistic Regression, Random Forest, XGBoost, Gradient Boosting
- **Class Imbalance Handling:** SMOTE implementation for improved predictions
- **Feature Engineering:** 14 engineered features from financial and behavioral data
- **Risk Segmentation:** Automated classification into Low/Medium/High risk tiers
- **Interactive Visualizations:** ROC curves, distribution plots, risk breakdowns
- **Basel III Compliance:** Regulatory-aligned ECL calculations

---

## 📁 Project Structure
```
credit-risk-ecl-modeling/
│
├── Credit_Risk_ECL_Analysis.ipynb    # Complete analysis notebook
├── loan_data.csv                     # Dataset (optional)
├── README.md                         # Project documentation
├── requirements.txt                  # Python dependencies
└── .gitignore                        # Git ignore file
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- pip package manager

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/richasudindesai2021-stack/credit-risk-ecl-modeling.git
cd credit-risk-ecl-modeling
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Run the notebook**
```bash
jupyter notebook Credit_Risk_ECL_Analysis.ipynb
```

4. **Update the file path** in the notebook to point to your data location

---

## 📊 Methodology

### 1. Data Preprocessing
- Handled missing values and outliers
- Converted categorical variables (employment length, credit line dates)
- Created binary default indicator from loan status

### 2. Feature Engineering
Created 14 predictive features:
- **Financial:** loan_amnt, int_rate, installment, annual_inc, dti
- **Credit Behavior:** delinq_2yrs, inq_last_6mths, open_acc, pub_rec
- **Account Info:** revol_bal, revol_util, total_acc
- **History:** emp_length_int, earliest_cr_line_months

### 3. PD (Probability of Default) Modeling
- Tested multiple algorithms: Logistic Regression, Random Forest, XGBoost, Gradient Boosting
- Applied SMOTE to handle class imbalance (40% default rate)
- Best model: XGBoost + SMOTE

### 4. LGD (Loss Given Default) Modeling
- Calculated actual loss rates for defaulted loans
- Used Random Forest Regressor for prediction
- Formula: `LGD = (Total Amount - Recoveries) / Total Amount`

### 5. EAD (Exposure at Default) Modeling
- Estimated outstanding exposure at time of default
- Used Random Forest Regressor
- Formula: `EAD = Outstanding Principal + Accrued Interest`

### 6. ECL Calculation
- **Final Formula:** `ECL = PD × LGD × EAD`
- Risk segmentation into Low/Medium/High tiers
- Portfolio-level aggregation

---

## 📈 Results

### Portfolio Metrics
| Metric | Value |
|--------|-------|
| Total Loans Analyzed | 600 |
| Total Portfolio Value | $10,925,436 |
| Total Exposure at Default | $5,955,586 |
| Total Expected Credit Loss | $649,218 |
| ECL Rate | 10.90% |

### Risk Metrics
| Metric | Value |
|--------|-------|
| Average PD | 40.34% |
| Average LGD | 27.04% |
| Average EAD | $9,926 |

### Risk Segmentation
| Risk Category | Count | Total ECL | Avg ECL |
|---------------|-------|-----------|---------|
| Low Risk | 7 | $6,206 | $887 |
| Medium Risk | 580 | $620,942 | $1,071 |
| High Risk | 13 | $22,070 | $1,698 |

**Key Insight:** While high-risk loans represent only 2.2% of the portfolio, they account for 3.4% of expected losses, indicating concentration risk.

---

## 🔧 Technologies Used

- **Python 3.8+**
- **pandas** - Data manipulation
- **numpy** - Numerical operations
- **scikit-learn** - Machine learning models
- **XGBoost** - Gradient boosting
- **imbalanced-learn** - SMOTE for class imbalance
- **matplotlib / seaborn** - Data visualization
- **Jupyter Notebook** - Interactive development

---

## 💡 Key Insights

1. **Model Performance:** The PD model performance indicates opportunities for enhancement through:
   - Incorporating macroeconomic indicators
   - Adding alternative data sources
   - Implementing ensemble techniques

2. **Risk Concentration:** Medium-risk loans drive 96% of expected losses despite being 97% of portfolio

3. **High Default Rate:** 40% default rate suggests subprime lending portfolio or economic stress period in data

4. **Capital Requirements:** Banks would need to reserve $649K (10.9% of portfolio) to cover expected losses under Basel III

---

## 🔮 Future Improvements

- [ ] Incorporate macroeconomic variables (GDP, unemployment rate, interest rates)
- [ ] Add alternative data sources (payment history, behavioral data)
- [ ] Implement deep learning models (Neural Networks)
- [ ] Build real-time scoring API
- [ ] Add stress testing scenarios
- [ ] Implement IFRS 9 staging logic
- [ ] Create interactive dashboard (Streamlit/Dash)
- [ ] Add model explainability (SHAP values)

---

## 📚 Data Requirements

Your dataset should include these columns:
- `loan_amnt` - Loan amount
- `int_rate` - Interest rate
- `installment` - Monthly payment
- `annual_inc` - Annual income
- `dti` - Debt-to-income ratio
- `loan_status` - Current loan status
- `emp_length` - Employment length
- `earliest_cr_line` - Earliest credit line date
- `delinq_2yrs` - Delinquencies in past 2 years
- `revol_bal` - Revolving balance
- `revol_util` - Revolving utilization
- Additional credit bureau fields

---

## 👤 Author

**Richa Sudin Desai**
- GitHub: [@richasudindesai2021-stack](https://github.com/richasudindesai2021-stack)
- LinkedIn: [Richa Desai](https://www.linkedin.com/in/richadesaiusc)
- Email: richasudin.desai2021@gmail.com

---

## 🙏 Acknowledgments

- Dataset inspired by LendingClub loan data
- Basel III framework guidelines
- IFRS 9 ECL methodology
- Scikit-learn and XGBoost communities

---

## 📞 Contact

For questions or collaboration opportunities, please reach out via:
- **GitHub Issues:** [Open an issue](https://github.com/richasudindesai2021-stack/credit-risk-ecl-modeling/issues)
- **Email:** richasudin.desai2021@gmail.com
- **LinkedIn:** [Connect with me](https://www.linkedin.com/in/richadesaiusc)

---

## ⭐ Star This Repository

If you find this project useful, please consider giving it a star! ⭐

---

## 📊 Sample Outputs

The notebook generates several analytical outputs:
- **ECL Results CSV** - Detailed loan-level calculations
- **ROC Curves** - Model performance comparison
- **Distribution Plots** - PD, LGD, EAD, and ECL visualizations
- **Risk Analysis Charts** - Segmentation and concentration analysis

---

*This project demonstrates practical application of credit risk modeling techniques for portfolio management and regulatory compliance.*
```

