
# 📊 Cybersecurity Job Dashboard - ReadMe

## 📁 Project Overview
The **Cybersecurity Job Dashboard** is an interactive Power BI application designed to help job seekers, career advisors, and hiring managers understand the cybersecurity job market using data visualizations and metrics. The dashboard provides deep insights into job availability, salary trends, experience level impact, remote work opportunities, domain specialization, and certification value.

This project was developed as part of the Master's Research Project under the guidance of Professor Maria Weber.

---

## 👥 Team Members and Contributions

| Team Member Name         | Contribution Area                                      |
|--------------------------|--------------------------------------------------------|
| **Aravind Kamuni**       | Power BI dashboard design, employment type analysis    |
| **Aravind Reddy Manda**  | Certification analytics, satisfaction trends           |
| **Lokender Yadav**       | Remote work and clearance analysis, visual validation  |
| **Prudhviraj Kancharla** | Key influencer model, year-wise trends                 |
| **Rajesh Kandukuri**     | Data validation using Python, domain analysis          |
| **Satish Kumar Kalla**   | Presentation, ER diagram design                        |

---

## 🧾 Dataset Summary

The dataset used was sourced from [Kaggle](https://www.kaggle.com/datasets/dannyrevaldo/salary-cyber-security-jobs) and includes over 2,500 cybersecurity job listings across various countries, roles, and employment types. The enhanced version was cleaned and transformed for quality assurance.

Key Fields:
- `job_title`, `salary_in_usd`, `experience_level`, `employment_type`
- `remote_ratio`, `Security Clearance Required`, `Certifications Preferred`
- `Primary Cybersecurity Domain`, `work_year`, `Job Satisfaction Rating`

---

## 🧪 Data Validation and Transformation

Performed in Python using Pandas (see `data_validation.py`). Steps included:
- Null/missing value check
- Salary and remote ratio validation
- Valid values for `experience_level`, `employment_type`, etc.
- Duplicate row removal
- Standardization of categorical values

Validation confirmed:
- No missing values
- Valid salary and remote ratios
- No duplicate records

---

## 🛠️ Project Structure

```
Cybersecurity-Job-Dashboard/
├── Enhanced_Cybersecurity_Job_Dataset.csv
├── data_validation.py
├── Cybersecurity Job Dashboard.pbix
├── Cybersecurity Job Dashboard.pdf
├── Traceability Matrix.pdf
├── ER-Diagram.pdf
├── Presentation.pdf
└── README.md
```

---

## 🧠 Application Features

### 1. 🌍 Country-Wise Job and Salary Insights
**Visuals:** Clustered bar chart - Count of job titles & average salary by location  
**DAX Used:**
```dax
Average Salary By Country = 
AVERAGEX(
    VALUES('JobData'[company_location]),
    CALCULATE(AVERAGE('JobData'[salary_in_usd]))
)
```

### 2. 🔍 Salary Influencers by Experience and Remote Ratio
**Visuals:** Key Influencer chart using `experience_level`, `remote_ratio`  
**DAX Used:**
```dax
Avg Salary Influencers = AVERAGE('JobData'[salary_in_usd])
```

### 3. 🧑‍💼 Top Paying Roles Over $100K
**Visuals:** Bar chart for top 5 highest paid roles  
**DAX Used:**
```dax
Top Paying Roles = 
TOPN(
    5,
    SUMMARIZE('JobData', 'JobData'[job_title], "AvgSalary", AVERAGE('JobData'[salary_in_usd])),
    [AvgSalary], DESC
)
```

### 4. 📈 Salary Trends Over Time
**Visuals:** Line chart over `work_year`  
**DAX Used:**
```dax
YOY Salary Growth = 
VAR PrevYear = CALCULATE(AVERAGE('JobData'[salary_in_usd]), PREVIOUSYEAR('JobData'[work_year]))
RETURN DIVIDE([Average Salary] - PrevYear, PrevYear)
```

### 5. 🛡️ Security Clearance Insights
**Visuals:** Pie chart + bar chart on salary by clearance type  
**DAX Used:**
```dax
% Jobs Requiring Clearance = 
DIVIDE(
    COUNTROWS(FILTER('JobData', 'JobData'[Security Clearance Required] <> "No")),
    COUNTROWS('JobData')
) * 100
```

### 6. 🏠 Remote Work Availability & Salary Comparison
**Visuals:** Bar chart and KPIs comparing salaries for remote/hybrid/onsite  
**DAX Used:**
```dax
% Fully Remote Jobs = 
DIVIDE(
    COUNTROWS(FILTER('JobData', 'JobData'[Remote Work Availability] = "Yes")),
    COUNTROWS('JobData')
) * 100
```

### 7. 🎓 Certifications and Their Impact
**Visuals:** Count of jobs & average salary per certification, trend line over years  
**DAX Used:**
```dax
Avg Salary by Cert = 
AVERAGEX(
    VALUES('JobData'[Certifications Preferred]),
    CALCULATE(AVERAGE('JobData'[salary_in_usd]))
)
```

### 8. 🧭 Cybersecurity Domain Analysis
**Visuals:** Domain-wise job distribution, average salary, and growth trend  
**DAX Used:**
```dax
Domain Salary = 
AVERAGEX(
    VALUES('JobData'[Primary Cybersecurity Domain]),
    CALCULATE(AVERAGE('JobData'[salary_in_usd]))
)
```

---

## 🖼️ Screenshot Highlights

### 🔸 Dashboard: Country-wise Metrics

<img width="1263" alt="Screenshot 2025-05-06 at 10 09 55 PM" src="https://github.com/user-attachments/assets/c47fdb53-a861-4a64-a1ec-2437e4144bbf" />

### 🔸 Dashboard: Salary by Certification

<img width="1263" alt="Screenshot 2025-05-06 at 10 10 30 PM" src="https://github.com/user-attachments/assets/97cf885c-a80d-4e61-ae56-421eaaaeabb9" />

<img width="1263" alt="Screenshot 2025-05-06 at 10 12 37 PM" src="https://github.com/user-attachments/assets/71ba2e47-4568-48d3-ac1a-311f086657a3" />

### 🔸 Dashboard: Remote vs Onsite Work Analysis and Clerance

<img width="1263" alt="Screenshot 2025-05-06 at 10 10 59 PM" src="https://github.com/user-attachments/assets/00250e54-eda7-4772-9ffb-452b116d4eca" />

### 🔸 Dashboard: Domains and CyberSecurity Fields

<img width="1263" alt="Screenshot 2025-05-06 at 10 13 00 PM" src="https://github.com/user-attachments/assets/1020413a-633d-49ae-9aa6-4f74137f119e" />

---

## 🧾 Files Included in the Submission

| File Name                               | Description                                    |
|-----------------------------------------|------------------------------------------------|
| `Enhanced_Cybersecurity_Job_Dataset.csv`| Final cleaned dataset                         |
| `data_validation.py`                    | Python script for data integrity checks       |
| `Cybersecurity Job Dashboard.pbix`      | Final Power BI Dashboard                      |
| `Cybersecurity Job Dashboard.pdf`       | PDF Export of Dashboard                       |
| `Traceability Matrix.pdf`               | Validation against project requirements       |
| `Presentation.pdf`                      | Final Presentation Deck                       |
| `ER-Diagram.pdf`                        | ER model used for planning (optional concept) |

---

## 🚀 Future Enhancements

- Real-time job market integration using API-based job feeds (e.g., LinkedIn, Indeed)
- Predictive analytics to forecast role demand and skill gaps
- Resume matcher feature using NLP
- Dynamic storytelling with guided walkthroughs

---

## 📬 Contact

For questions or access to this dashboard:
> Contact any team member or Professor Maria Weber at [SLU Faculty]

---

© 2025 | Team 9 | Saint Louis University – Health Informatics & Analytics
