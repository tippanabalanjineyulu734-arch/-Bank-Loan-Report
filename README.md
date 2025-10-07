

# 🏦 Bank Loan Report – SQL KPI Framework & Dashboard Integration

## 📌 Project Title
**Bank Loan Report – KPI Tracking, Loan Segmentation & BI Dashboard Integration**

## 🧰 Tools Used
- **SQL** – for KPI extraction, segmentation logic, and query optimization  
- **Power BI** – for dynamic dashboards and stakeholder-ready visuals  
- **Excel Automation** – for reporting workflows and MTD/PMTD comparisons  
- **Python (pandas)** – for data preprocessing and automation  
- **GitHub** – for version control and documentation  

## 🧠 Project Context
This project simulates a real-world loan analytics dashboard for a financial institution. It includes over 30 modular SQL queries designed to track key performance indicators, segment loan statuses, and support interactive BI dashboards. The queries are structured to support MTD/PMTD analysis, good vs. bad loan classification, and dimensional breakdowns by month, state, term, and borrower attributes.

---

## 📊 Summary KPIs

- **Total Loan Applications**
  ```sql
  SELECT COUNT(id) AS Total_Applications FROM bank_loan_data
  ```

- **MTD / PMTD Applications**
  ```sql
  SELECT COUNT(id) FROM bank_loan_data WHERE MONTH(issue_date) = 12
  SELECT COUNT(id) FROM bank_loan_data WHERE MONTH(issue_date) = 11
  ```

- **Total Funded Amount**
  ```sql
  SELECT SUM(loan_amount) FROM bank_loan_data
  ```

- **Total Amount Received**
  ```sql
  SELECT SUM(total_payment) FROM bank_loan_data
  ```

- **Average Interest Rate & DTI**
  ```sql
  SELECT AVG(int_rate)*100 AS Avg_Int_Rate FROM bank_loan_data
  SELECT AVG(dti)*100 AS Avg_DTI FROM bank_loan_data
  ```

---

## ✅ Good vs. Bad Loan Segmentation

- **Good Loan Percentage**
  ```sql
  SELECT (COUNT(CASE WHEN loan_status IN ('Fully Paid', 'Current') THEN id END) * 100.0) / COUNT(id) AS Good_Loan_Percentage FROM bank_loan_data
  ```

- **Bad Loan Percentage**
  ```sql
  SELECT (COUNT(CASE WHEN loan_status = 'Charged Off' THEN id END) * 100.0) / COUNT(id) AS Bad_Loan_Percentage FROM bank_loan_data
  ```

- **Good Loan Applications / Funded / Received**
  ```sql
  SELECT COUNT(id) FROM bank_loan_data WHERE loan_status IN ('Fully Paid', 'Current')
  SELECT SUM(loan_amount) FROM bank_loan_data WHERE loan_status IN ('Fully Paid', 'Current')
  SELECT SUM(total_payment) FROM bank_loan_data WHERE loan_status IN ('Fully Paid', 'Current')
  ```

- **Bad Loan Applications / Funded / Received**
  ```sql
  SELECT COUNT(id) FROM bank_loan_data WHERE loan_status = 'Charged Off'
  SELECT SUM(loan_amount) FROM bank_loan_data WHERE loan_status = 'Charged Off'
  SELECT SUM(total_payment) FROM bank_loan_data WHERE loan_status = 'Charged Off'
  ```

---

## 📈 Loan Status Breakdown

```sql
SELECT loan_status, COUNT(id), SUM(total_payment), SUM(loan_amount), AVG(int_rate*100), AVG(dti*100)
FROM bank_loan_data
GROUP BY loan_status
```

```sql
SELECT loan_status, SUM(total_payment), SUM(loan_amount)
FROM bank_loan_data
WHERE MONTH(issue_date) = 12
GROUP BY loan_status
```

---

## 🗂️ Overview by Dimensions

- **By Month**
  ```sql
  SELECT MONTH(issue_date), DATENAME(MONTH, issue_date), COUNT(id), SUM(loan_amount), SUM(total_payment)
  FROM bank_loan_data
  GROUP BY MONTH(issue_date), DATENAME(MONTH, issue_date)
  ORDER BY MONTH(issue_date)
  ```

- **By State**
  ```sql
  SELECT address_state, COUNT(id), SUM(loan_amount), SUM(total_payment)
  FROM bank_loan_data
  GROUP BY address_state
  ORDER BY address_state
  ```

- **By Term**
  ```sql
  SELECT term, COUNT(id), SUM(loan_amount), SUM(total_payment)
  FROM bank_loan_data
  GROUP BY term
  ORDER BY term
  ```

- **By Employee Length**
  ```sql
  SELECT emp_length, COUNT(id), SUM(loan_amount), SUM(total_payment)
  FROM bank_loan_data
  GROUP BY emp_length
  ORDER BY emp_length
  ```

- **By Purpose**
  ```sql
  SELECT purpose, COUNT(id), SUM(loan_amount), SUM(total_payment)
  FROM bank_loan_data
  GROUP BY purpose
  ORDER BY purpose
  ```

- **By Home Ownership**
  ```sql
  SELECT home_ownership, COUNT(id), SUM(loan_amount), SUM(total_payment)
  FROM bank_loan_data
  GROUP BY home_ownership
  ORDER BY home_ownership
  ```

---

## 🔍 Filter Example – Grade A Loans

```sql
SELECT purpose, COUNT(id), SUM(loan_amount), SUM(total_payment)
FROM bank_loan_data
WHERE grade = 'A'
GROUP BY purpose
ORDER BY purpose
```

---

## 🛠️ Skills Demonstrated

- Advanced SQL for KPI tracking and business rule logic  
- Power BI dashboard design with filter-responsive queries  
- Python for data cleaning and automation  
- Financial domain modeling: loan risk, interest, DTI, repayment  
- Data storytelling and stakeholder-ready documentation  
- Modular query design for scalable analytics workflows  

---

## 📬 Contact

**balanjineeyulu T**  
📞 6360673989  
📧 topanabalanjineeyulu743@gmail.com  
💼 Data Analyst | SQL • Power BI • Python • Excel
```

---

