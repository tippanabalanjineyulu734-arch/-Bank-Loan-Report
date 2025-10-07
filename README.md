
# 💼 Dark Loan Report – Predicting Loan Defaults with ML

## 🧠 Project Overview
This project analyzes high-risk loans using the Lending Club dataset. It applies machine learning and statistical techniques to identify patterns in loan defaults, helping financial institutions improve risk assessment and lending strategies.

---

## 🎯 Business Objective
To support credit risk teams and loan officers in:
- Identifying loans likely to default before approval
- Understanding key drivers of loan performance
- Enhancing underwriting policies and interest rate modeling
- Reducing financial losses through predictive analytics

---

## 📊 Key Insights
- Loans with FICO scores below 660 showed a 3x higher default rate
- Interest rates above 18% correlated with early payment failures
- Grade D and E loans had poor recovery performance
- Employment length and annual income were weak predictors compared to loan purpose and term

---

## 🛠️ Tools & Technologies
| Tool            | Purpose                                  |
|------------------|-------------------------------------------|
| Python (pandas, numpy) | Data cleaning & transformation         |
| scikit-learn     | Model training & evaluation               |
| matplotlib, seaborn | Data visualization & EDA                 |
| Jupyter Notebook | Interactive analysis & reporting          |

---

## 📁 Dataset
- **Source**: [Lending Club Public Dataset](https://www.lendingclub.com/info/download-data.action)
- **Fields Used**: loan_status, term, interest_rate, grade, annual_income, FICO score, purpose, employment_length

---

## 🚀 How to Run
1. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```
2. Launch the notebook:
   ```bash
   jupyter notebook Dark_Loan_Report.ipynb
   ```
3. Follow the notebook cells for EDA, model training, and insights.

---

## 📈 Model Performance
| Model         | Accuracy | Precision | Recall | AUC-ROC |
|---------------|----------|-----------|--------|---------|
| Logistic Regression | 78%      | 0.81      | 0.76   | 0.84    |
| Random Forest       | 85%      | 0.87      | 0.82   | 0.89    |

---

## 📌 File Structure
```
├── Dark_Loan_Report.ipynb
├── lending_club_data.csv
├── visuals/
│   ├── default_heatmap.png
│   └── roc_curve.png
├── README.md
└── LICENSE.md
```

---

## 📣 Future Enhancements
- Integrate Power BI dashboard for stakeholder reporting
- Add SHAP values for model interpretability
- Deploy model via Flask for real-time scoring

---

## 📜 License
This project is licensed under the MIT License – see `LICENSE.md` for details.


