#   Salifort Motors HR Analytics Capstone
[View salifort Dataset on Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv)


##  Project Overview
This project was completed as part of the **Google Advanced Data Analytics Professional Certificate Capstone**. The objective is to analyze employee data from **Salifort Motors**, a large consulting company, to understand factors that lead to employee turnover and to develop a predictive model that helps the HR department proactively retain employees.

---

##   Problem Statement
The HR department is facing high employee churn. They have collected internal employee records but are unsure how to use them for actionable insights. The goal is to:
- Identify drivers of churn
- Predict future churn risk
- Recommend strategic HR actions to improve retention

Solving this problem through predictive analytics enables proactive interventions, allowing HR to focus resources on at-risk employees and address systemic issues, thereby improving overall organizational stability and efficiency.

## Business Value & Impact
Employee turnover is a costly challenge for any organization, encompassing expenses related to recruitment, onboarding, training new hires, and lost productivity. This project delivers substantial business value by:

Cost Reduction: Proactively identifying at-risk employees and implementing targeted retention strategies can significantly reduce the financial burden of replacing talent (estimated to be 1.5-2x an employee's salary).

Improved Employee Morale & Productivity: Addressing the root causes of dissatisfaction can lead to a more engaged and productive workforce.

Strategic Decision Support: Providing HR with empirical evidence to support policy changes, resource allocation, and talent management initiatives.

Enhanced Workforce Planning: Enabling more accurate forecasting of staffing needs and potential gaps.

---

## 📊 Dataset
The analysis is based on a comprehensive HR dataset sourced from Kaggle (HR Analytics and Job Prediction). The dataset comprises 14,999 rows and 10 features, providing a rich basis for understanding employee behavior.


| Column Name            | Description                                  |
|------------------------|----------------------------------------------|
| `satisfaction_level`   | Employee satisfaction score (0–1)            |
| `last_evaluation`      | Last evaluation score (0–1)                  |
| `number_project`       | Number of projects assigned                  |
| `average_montly_hours` | Average monthly working hours                |
| `time_spend_company`   | Years spent at the company                   |
| `Work_accident`        | Whether they had a work accident             |
| `promotion_last_5years`| Was promoted in last 5 years (0/1)           |
| `Department`           | Department name                              |
| `salary`               | Salary level (`low`, `medium`, `high`)       |
| `left`                 | Target variable (1 = left, 0 = stayed)       |

Dataset Source: Simulated HR dataset inspired by real-world churn prediction scenarios. *(Included in `/data/raw/HR_comma_sep.csv`)*

---

##   Project Goals


**Exploratory Data Analysis (EDA)**: Conduct in-depth EDA to uncover initial patterns, correlations, and anomalies within the HR dataset, focusing on potential drivers of churn.

**Feature Engineering**: Develop new features or transform existing ones to enhance the predictive power of the models, such as identifying combinations of factors indicating dissatisfaction.

**Predictive Model Building**: Develop and evaluate classification models to predict whether an employee will leave the company. This includes experimenting with:

-**Logistic Regression**

-**Decision Trees**

-**Random Forest**

**Model Evaluation & Interpretation**: Rigorously assess model performance using appropriate metrics (accuracy, precision, recall, F1-score, AUC) and interpret model outputs to identify the most impactful features.

**Actionable Business Recommendations**: Translate analytical findings into clear, concise, and implementable recommendations for the HR department to reduce turnover and improve employee satisfaction.
---

##  Tools & Technologies Used

-**Programming Language**: Python
-**Data Manipulation**: pandas, numpy
-**Data Visualization**: matplotlib.pyplot, seaborn
-**Machine Learning**: scikit-learn (for model building, preprocessing, and evaluation)
-**Notebook Environment**: Jupyter Notebook
-**Model Persistence**: pikle (for general Python object serialization)
-**Version Control**: Git & GitHub

---
##  Exploratory Data Analysis (EDA) & Key Insights
The initial EDA revealed several compelling patterns critical for understanding employee churn:

**Satisfaction Level as a Key Indicator**: A significantly higher proportion of employees who left had very low satisfaction levels (below 0.2) or surprisingly high levels (above 0.7), suggesting two distinct groups of leavers: those who are clearly unhappy and those who might be "quiet quitters" or seeking new opportunities after high performance.

**Workload and Evaluation**: Employees leaving often had a high number_project, high average_monthly_hours, and disproportionately high last_evaluation scores, indicating burnout or feeling undervalued despite strong performance.

**Time Spent in Company**: Employees with 4-5 years of time_spend_company showed a higher propensity to leave, potentially hitting a career plateau or seeking external growth.

**Salary and Promotion**: Unsurprisingly, employees with low and medium salaries, and those who had not received a promotion_last_5years, were more likely to churn.

These initial insights directly informed the feature engineering process, allowing for the creation of composite features to better capture complex relationships.
## 📈 Results Summary

### Logistic Regression Model:

**Accuracy**: 83%
**Precision (weighted avg)**: 80%
**Recall (weighted avg)**: 83%
**F1-Score (weighted avg)**: 80%

This model provided a good baseline, offering interpretability into the linear relationships driving churn.

### Tree-based Machine Learning Models (Decision Tree & Random Forest):

Feature engineering significantly boosted the performance of these models.

### Decision Tree Model:

**AUC**: 93.8%
**Precision**: 87.0%
**Recall**: 90.4%
**F1-Score**: 88.7%
**Accuracy**: 96.2%

### Random Forest Model:

**AUC**: 93.8%
**Precision**: 87.0%
**Recall**: 90.4%
**F1-Score**: 88.7%
**Accuracy**: 96.2%


**Overall Accuracy**: 89% 

Outperformed the Decision Tree modestly, demonstrating superior generalization capabilities due to its ensemble nature.

The Random Forest model proved to be the most robust and accurate predictor of employee churn, making it the recommended model for deployment.

The models successfully identified that low satisfaction levels, prolonged tenure (e.g., 4-5 years without significant change), and lower salary tiers are the most prominent indicators of an employee's likelihood to leave. Additionally, high workload coupled with high performance evaluations suggests a burnout risk.

Top churn indicators (based on feature importance):
1. **Low satisfaction_level**
2. **High time_spend_company**
3. **Average monthly hours**
4. **Low salary**
5. **Lack of promotion in last 5 years**

### 🧩 Business Insights:
- Employees with low satisfaction and no promotions are at higher churn risk.
- Employees working excessive hours (without promotion) are more likely to leave.
- Lower salary brackets have significantly higher churn rates.

### 💡 Strategic Recommendations:
- Launch targeted retention programs for at-risk employees.
- Create work-life balance initiatives in high-hour departments.
- Adjust promotion and performance recognition strategies.
- Reevaluate compensation models for employees in key departments.

### Ethical Considerations
This project was developed with a strong emphasis on ethical data handling and responsible AI practices:

**Fairness and Bias**: Efforts were made to ensure the model does not inadvertently discriminate based on sensitive attributes. While department and salary are included as features due to their direct business relevance to churn, careful consideration would be given in deployment to prevent their misuse in ways that could lead to unfair treatment.

**Transparency**: The use of interpretable models like Decision Trees (and feature importance from Random Forest) allows for understanding why a prediction is made, rather than being a "black box."

**Privacy**: The dataset was anonymized, and no personally identifiable information (PII) was used. In a real-world scenario, strict data governance and privacy protocols would be adhered to.

**Impact on Employees**: Recommendations are framed to improve employee well-being and satisfaction, rather than solely focusing on cost-cutting at the expense of employees.

Detailed results and visuals are available in:
📂 `reports/results_summary.pdf`  
📂 `visuals/` — includes charts like churn by department, satisfaction distributions, ROC curve

.
├── README.md                           # This README file.
├── Jupyter notebooks
    └── Salifort_motors_data_cleaning_and_EDA.ipynb.       # jupyter notebook contains EDA and data       preprocessing
    └── Salifort_motors_Logistic_Regression_Model.ipynb      # jupyter notebook contains Logistic_Regression_Model
    └──  Salifort_motors_Tree-based_Machine_Learning_model.ipynb   # jupyter notebook contains Tree-based_Machine_Learning_model
├──
├── Data
    └── HR_dataset.csv                 # The raw dataset used for the project.
└── models/                             # Directory for saving trained models (e.g., joblib files).
    └── Employee Churn at Salifort Motorshr_rf1.pickle    # Saved models
    └── Employee Churn at Salifort Motorshr_rf2.pickle


---


