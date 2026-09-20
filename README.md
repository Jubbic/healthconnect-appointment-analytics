# HealthConnect Appointment Analytics

AnalystLab Africa Experience Lab - Data Analytics Track 

Intern: Adeleke Jubril Adedeji

## Project Overview

HealthConnect Clinic is a fictional healthcare provider dealing with a common challenge: patients missing their scheduled appointments. The main aim of this project is to use the available data to understand why these missed appointments happen and identify patterns that could help the clinic make better decisions.

This is a multi-week project, and each week builds on the work from the previous one:

Problem Understanding → Analysis & Solution Design → Development → Testing & Refinement → Final Presentation

## Central Project Question

How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?

## Dataset

The analysis was carried out using:

- `HealthConnect_Appointment_Data.csv` 5,000 fictional and anonymised appointment records covering patient demographics, booking behaviour, reminders, clinic logistics, and appointment outcomes.
- `HealthConnect_Data_Dictionary` Used to understand the variables and what each column represents.

## Week 4: Problem Understanding

Week 4 was mainly about getting familiar with the data and understanding what might be contributing to missed appointments before moving into deeper analysis.

**What I did:**
- Reviewed the dataset structure and compared it with the data dictionary
- Checked the data for missing values, duplicates, and other possible inconsistencies
- Explored the variables against appointment outcomes to see which factors showed noticeable patterns
- Came up with 5 business questions and 5 KPIs based on what I found in the data
- Planned the main areas to focus on in Week 5

**Key findings:**
- The dataset was generally clean, with no duplicate records or major logical issues
- Booking lead time and previous no-show history showed the strongest relationship with appointment outcomes
- Reminder status showed some effect, but it was not as strong as the two factors above
- Appointment day, gender and distance to the clinic showed little to no meaningful relationship with whether an appointment was missed

## Week 5: Analysis & KPI Development

Week 5 moved from initial problem understanding into practical implementation, building on the Week 4 findings without starting over.

**What I did:**
- Calculated and visualised the 5 proposed KPIs
- Went deeper into the strongest predictors booking lead time and previous no-show history
- Looked at how booking lead time, previous no-shows and reminders interact with each other
- Built an initial dashboard and produced 6 business insights
- Documented a cross-track collaboration point and updated assumptions/risks from Week 4

**Key findings:**
- Booking lead time and previous no-show history compound patients booking 31-60 days out with 3+ prior no-shows reached an 81% no-show rate
- Reminders appeared more effective for patients with a history of missed appointments than for low-risk patients
- The 20-50km distance segment showed a noticeably higher no-show rate than closer patients

## Week 6: Integration, Advanced Development & Validation

Week 6 shifted from producing new EDA to validating and integrating the Week 5 work, and connecting it with another track rather than working in isolation.

**What I did:**
- Converted the lead time × previous no-shows interaction into a composite risk score, validated with a chi-square test and compared against alternative feature representations using AUC
- Statistically re-tested the reminder-effectiveness and distance findings rather than relying on descriptive percentages alone
- Narrowed the reminder-targeting recommendation where deeper testing only partly supported the original Week 5 claim
- Refreshed the dashboard around the validated risk tiers
- Produced a validated feature handoff file for the Data Science track (cross-track integration evidence)

**Key findings:**
- The composite risk score separates no-show risk cleanly and significantly (22.8% to 81.0% across score levels, p<0.0001), but the raw underlying features outperform the bucketed score for prediction (AUC 0.679 vs 0.658)
- The "targeted reminders help high-risk patients" claim only holds up statistically for patients with exactly 2 prior no-shows (p=0.032) narrowed from the broader Week 5 claim
- The 20-50km distance effect is statistically significant (p=0.0002) and not explained by appointment type a standalone effect
- The "Very High" risk tier (~5% of appointments, 76.1% no-show rate) is a small, high-value group for manual case management

## Week 7: Testing, Refinement & End-to-End Validation

Week 7 moved from building and integrating new work into systematically testing and validating what was already delivered in Week 6, including a genuine cross-track (HC-POD) validation activity rather than a repeat of the Week 6 integration.

**What I did:**
- Independently re-derived the composite risk score from raw data and confirmed it reproduces the exact Week 6 reported figures
- Tested whether the risk pattern holds within every appointment type and age group individually, not just in aggregate
- Retested the distance finding using quantile-based bins instead of the original fixed bins
- Retested the reminder-effectiveness finding using effect size (Cohen's h) instead of relying on p-values alone
- Ran an HC-POD cross-track test on the Week 6 Data Science handoff file checking it for nulls, duplicate keys and internal consistency
- Refined the dashboard's reminder chart to reflect the dimension that was actually tested

**Key findings:**
- The composite risk score, and the distance and reminder findings, all held up under independent retesting no reversals
- The cross-track test on the handoff file found a real issue: 86 unflagged missing values in `distance_to_clinic_km` (1.8% of rows)
- Fixed by adding an explicit `distance_missing` indicator column and re-exporting the file (now 10 columns instead of 9) — Data Science should use this corrected version going forward

## Files in This Repository

| File | Description |
|---|---|
| HealthConnect_Week4_Initial_Analysis_Adeleke_Jubril.ipynb | Dataset review, data quality checks, exploratory analysis, business questions, and proposed KPIs |
| HealthConnect_Week4_Project_Summary_Adeleke_Jubril.docx | Summary of Week 4 work and planned focus for Week 5 |
| HealthConnect_Appointment_Data.csv | Dataset used for the analysis |
| HealthConnect_Data_Dictionary_Adeleke_Jubril.xlsx | Data dictionary and variable definitions |
| week5/HealthConnect_Week5_Analysis_Adeleke_Jubril.ipynb | Deeper EDA, KPI calculations, dashboard, and business insights building on Week 4 |
| week5/HealthConnect_Week5_Project_Summary_Adeleke_Jubril.docx | Summary of Week 5 work and planned focus for Week 6 |
| week6/HealthConnect_Week6_Advanced_Analytics_Adeleke_Jubril.ipynb | Validated composite risk score, revised findings, refined KPIs, and updated dashboard building on Week 5 |
| week6/HealthConnect_Week6_Project_Summary_Adeleke_Jubril.docx | Summary of Week 6 work and planned focus for Week 7 |
| week6/HealthConnect_Week6_RiskFeature_DataScience_Handoff.csv | Original validated risk feature file produced for the Data Science track (cross-track integration evidence) |
| week7/HealthConnect_Week7_Testing_Refinement_Adeleke_Jubril.ipynb | Testing/validation log, KPI reproducibility checks, segment-stability testing, retested findings, refined dashboard, and HC-POD cross-track testing building on Week 6 |
| week7/HealthConnect_Week7_Project_Summary_Adeleke_Jubril.docx | Summary of Week 7 work and planned focus for Week 8 |
| week7/HealthConnect_Week6_RiskFeature_DataScience_Handoff.csv | Corrected version of the Week 6 handoff file (added distance_missing flag after testing found unflagged nulls) |

## Tools Used

Python: Pandas, NumPy, Matplotlib, Seaborn, SciPy, scikit-learn  
Environment: Jupyter Notebook

## Next Steps - Week 8

For Week 8, I'll be focusing on:

- Final integration of the tested and validated Week 7 outputs
- Confirming Data Science has picked up the corrected risk-feature handoff file
- Preparing final presentation materials

## Repo Structure

- **Root:** Week 4 files (initial analysis notebook, project summary, dataset, data dictionary) submitted for grading, kept in place until results are returned
- **week5/:** Week 5 analysis notebook and project summary deeper EDA, KPI calculations, dashboard, and business insights building on Week 4
- **week6/:** Week 6 analysis notebook, project summary, and original Data Science handoff file validated risk score, revised findings, and cross-track integration building on Week 5
- **week7/:** Week 7 testing/validation notebook, project summary, and corrected Data Science handoff file retested findings and HC-POD cross-track testing building on Week 6
