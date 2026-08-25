# HealthConnect Appointment Analytics

**AnalystLab Africa Experience Lab — Data Analytics Track**  
**Intern:** Adeleke Jubril Adedeji

## Project Overview

HealthConnect Clinic is a fictional healthcare provider dealing with a common challenge: patients missing their scheduled appointments. The main aim of this project is to use the available data to understand why these missed appointments happen and identify patterns that could help the clinic make better decisions.

This is a multi-week project, and each week builds on the work from the previous one:

**Problem Understanding → Analysis & Solution Design → Development → Testing & Refinement → Final Presentation**

## Central Project Question

**How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?**

## Dataset

The analysis was carried out using:

- **`HealthConnect_Appointment_Data.csv`** — 5,000 fictional and anonymised appointment records covering patient demographics, booking behaviour, reminders, clinic logistics, and appointment outcomes.
- **`HealthConnect_Data_Dictionary`** — Used to understand the variables and what each column represents.

## Week 4: Problem Understanding

Week 4 was mainly about getting familiar with the data and understanding what might be contributing to missed appointments before moving into deeper analysis.

### What I Did

- Reviewed the dataset structure and compared it with the data dictionary.
- Checked the data for missing values, duplicates, and other possible inconsistencies.
- Explored the variables against appointment outcomes to see which factors showed noticeable patterns.
- Came up with **5 business questions and 5 KPIs** based on what I found in the data.
- Planned the main areas I will focus on in Week 5.

### Key Findings

A few things stood out during the initial analysis:

- The dataset was generally clean, with no duplicate records or major logical issues.
- **Booking lead time** and **previous no-show history** showed the strongest relationship with appointment outcomes.
- Reminder status showed some effect, but it was not as strong as the two factors above.
- Appointment day, gender, and distance to the clinic showed little to no meaningful relationship with whether an appointment was missed.

These findings will guide the next stage of the project rather than relying on assumptions about what might be causing no-shows.

## Files in This Repository

| File | Description |
|---|---|
| `HealthConnect_Week4_Initial_Analysis_Adeleke_Jubril.ipynb` | Contains the dataset review, data quality checks, exploratory analysis, business questions, and proposed KPIs |
| `HealthConnect_Week4_Project_Summary_Adeleke_Jubril.docx` | Summary of my Week 4 work and the planned focus for Week 5 |
| `HealthConnect_Appointment_Data.csv` | Dataset used for the analysis |
| `HealthConnect_Data_Dictionary_Adeleke_Jubril.xlsx` | Data dictionary and variable definitions |

## Tools Used

**Python:** Pandas, NumPy, Matplotlib, Seaborn  
**Environment:** Jupyter Notebook

## Next Steps — Week 5

For Week 5, I’ll be focusing on:

- Calculating and visualising the **5 proposed KPIs**
- Going deeper into the strongest predictors, especially booking lead time and previous no-show history
- Looking at how some of the factors may interact with each other
- Starting to organise the findings into something that can eventually become a dashboard or business-facing report
