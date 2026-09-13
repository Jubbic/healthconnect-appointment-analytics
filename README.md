# HealthConnect Appointment Analytics

**AnalystLab Africa Experience Lab - Data Analytics Track**
**Intern:** Adeleke Jubril Adedeji

## Project Overview

HealthConnect Clinic is a fictional healthcare provider facing a common problem: patients missing their scheduled appointments.

The goal of this project is to use appointment data to understand what may be contributing to missed appointments and identify patterns that could help the clinic make better decisions.

This is a multi-week project, with each week building on the previous work:

**Problem Understanding → Analysis & Solution Design → Development → Testing & Refinement → Final Presentation**

## Central Project Question

How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?

## Dataset

The analysis uses:

* `HealthConnect_Appointment_Data.csv` — 5,000 fictional and anonymised appointment records covering patient demographics, booking behaviour, reminders, clinic logistics, and appointment outcomes.
* `HealthConnect_Data_Dictionary` — Used to understand the variables and what each column represents.

## Week 4: Problem Understanding

Week 4 was mainly about getting familiar with the data and understanding what might be contributing to missed appointments before moving into deeper analysis.

**What I did:**

* Reviewed the dataset structure and compared it with the data dictionary.
* Checked for missing values, duplicates, and other possible data issues.
* Explored the variables against appointment outcomes to see which factors showed noticeable patterns.
* Developed 5 business questions and 5 KPIs based on the initial findings.
* Planned the main areas to investigate in Week 5.

**Key findings:**

* The dataset was generally clean, with no duplicate records or major logical issues.
* Booking lead time and previous no-show history showed the strongest relationship with appointment outcomes.
* Reminder status showed some effect, but it was not as strong as the two factors above.
* Appointment day, gender, and distance to the clinic showed little to no meaningful relationship with whether an appointment was missed.

## Week 5: Analysis & KPI Development

Week 5 built on the initial findings from Week 4. Instead of starting over, I focused on the factors that looked most important and turned them into more practical analysis.

**What I did:**

* Calculated and visualised the 5 proposed KPIs.
* Investigated booking lead time and previous no-show history in more detail.
* Looked at how booking lead time, previous no-shows, and reminders interact with one another.
* Built an initial dashboard and identified 6 business insights.
* Documented a cross-track collaboration point and updated the assumptions and risks from Week 4.

**Key findings:**

* Booking lead time and previous no-show history appear to compound. Patients booking 31–60 days in advance with 3 or more previous no-shows reached an 81% no-show rate.
* Reminders appeared to be more effective for patients with a history of missed appointments than for low-risk patients.
* Patients in the 20–50km distance segment had a noticeably higher no-show rate than patients living closer to the clinic.

## Week 6: Advanced Analytics, Validation & Integration

Week 6 was about testing whether the Week 5 findings actually held up statistically, refining the recommendations, and connecting the work with the Data Science track.

**What I did:**

* Created a composite risk score using booking lead time and previous no-show history.
* Used a chi-square test to validate the relationship between the risk score and appointment outcomes.
* Compared the composite score with the original features using AUC to see which representation was better for prediction.
* Re-tested the reminder-effectiveness and distance findings instead of relying only on descriptive percentages.
* Narrowed the reminder-targeting recommendation where the deeper testing did not fully support the original Week 5 claim.
* Updated the dashboard around the validated risk tiers.
* Produced a validated feature handoff file for the Data Science track.

**Key findings:**

* The composite risk score showed a clear and statistically significant difference in no-show rates, ranging from 22.8% to 81.0% across score levels (p<0.0001). However, the original features performed better for prediction, with an AUC of 0.679 compared with 0.658 for the bucketed score.
* The Week 5 claim that targeted reminders help high-risk patients was too broad. The statistical evidence only supported the effect for patients with exactly 2 prior no-shows (p=0.032).
* The 20–50km distance effect was statistically significant (p=0.0002) and was not explained by appointment type, suggesting it may be an independent factor.
* The “Very High” risk tier represents about 5% of appointments but has a 76.1% no-show rate, making it a small but potentially valuable group for manual follow-up.

## Files in This Repository

| File                                                                | Description                                                                                              |
| ------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `HealthConnect_Week4_Initial_Analysis_Adeleke_Jubril.ipynb`         | Dataset review, data quality checks, exploratory analysis, business questions, and proposed KPIs         |
| `HealthConnect_Week4_Project_Summary_Adeleke_Jubril.docx`           | Summary of Week 4 work and planned focus for Week 5                                                      |
| `HealthConnect_Appointment_Data.csv`                                | Dataset used for the analysis                                                                            |
| `HealthConnect_Data_Dictionary_Adeleke_Jubril.xlsx`                 | Data dictionary and variable definitions                                                                 |
| `week5/HealthConnect_Week5_Analysis_Adeleke_Jubril.ipynb`           | Deeper EDA, KPI calculations, dashboard, and business insights building on Week 4                        |
| `week5/HealthConnect_Week5_Project_Summary_Adeleke_Jubril.docx`     | Summary of Week 5 work and planned focus for Week 6                                                      |
| `week6/HealthConnect_Week6_Advanced_Analytics_Adeleke_Jubril.ipynb` | Validated composite risk score, revised findings, refined KPIs, and updated dashboard building on Week 5 |
| `week6/HealthConnect_Week6_Project_Summary_Adeleke_Jubril.docx`     | Summary of Week 6 work and planned focus for Week 7                                                      |
| `week6/HealthConnect_Week6_RiskFeature_DataScience_Handoff.csv`     | Validated risk feature file produced for the Data Science track                                          |

## Tools Used

* **Python:** Pandas, NumPy, Matplotlib, Seaborn, SciPy, scikit-learn
* **Environment:** Jupyter Notebook

## Next Steps - Week 7

For Week 7, I'll be focusing on:

* Testing, refining, and validating the work completed so far.
* Re-testing the reminder and distance findings if new data becomes available.
* Coordinating with the Data Science track once their model using the handed-off risk feature is available.
* Tracking outcomes if the risk-tier approach is adopted operationally.

## Repo Structure

* **Root:** Week 4 files, including the initial analysis notebook, project summary, dataset, and data dictionary. These are being kept in place until the grading results are returned.
* **`week5/`:** Week 5 analysis notebook and project summary, covering deeper EDA, KPI calculations, dashboard development, and business insights.
* **`week6/`:** Week 6 analysis notebook, project summary, and Data Science handoff file, covering the validated risk score, revised findings, and cross-track integration.
