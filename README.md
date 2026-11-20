# CareLoop Clinics – No-Show Guard

## Project Overview
CareLoop Clinics – No-Show Guard is a data analytics and machine learning project designed to understand and predict patient appointment no-shows. The project combines Python, SQL, Machine Learning, and Generative AI to identify patterns, evaluate no-show risks, and generate actionable insights for clinics.

## Project Objectives
- Clean and analyse appointment data.
- Identify clinic-wise, monthly, and lead-time no-show trends.
- Build machine learning models to predict appointment no-shows.
- Analyse patient follow-up notes using Generative AI.
- Provide data-driven recommendations to reduce missed appointments.

## Tech Stack
- Python, Pandas, NumPy
- Matplotlib, Seaborn
- MySQL
- Scikit-learn
- Logistic Regression, Decision Tree, Random Forest
- Google Gemini API
- Pydantic
- Google Colab

## Project Workflow

### Part 1: Data Cleaning and Exploratory Data Analysis
- Cleaned appointment records and handled missing values, duplicates, and outliers.
- Standardised booking channels and prepared appointment features.
- Calculated lead days and created a binary no-show target.
- Enriched clinic data with temperature information.

**Final Dataset:** 990 appointments across 8 clinics.

### Part 2: SQL Analysis
Used MySQL to perform:
- Data validation and aggregation.
- Clinic-wise no-show analysis.
- Lead-time band analysis.
- Monthly no-show trends using window functions and LAG.
- City-wise ranking and comparison.

### Part 3: Machine Learning
Built and evaluated:
- Logistic Regression
- Decision Tree
- Random Forest

Selected Logistic Regression based on the highest cross-validation ROC-AUC.

**Final Model Results (Test Set, Threshold = 0.35):**
- Accuracy: 78.79%
- Precision: 57.14%
- Recall: 57.14%
- F1-score: 57.14%
- ROC-AUC: 78.89%

### Part 4: Generative AI Analysis
- Used Google Gemini API to analyse patient follow-up notes.
- Applied structured prompting and JSON responses.
- Used Pydantic for output validation.
- Compared simple prompting with CRAFT prompting.
- Merged AI-generated insights with appointment and reminder data.

Analysed 10 follow-up notes, including one blank note that was skipped.

## Key Findings
- Overall appointment no-show rate was approximately 22.02%.
- Appointments booked 31 or more days in advance had a 60.5% no-show rate (26 out of 43).
- Appointments with 15–30 days of lead time had a 30.0% no-show rate.
- Lead time was an important feature in the machine learning analysis.
- The GenAI analysis identified multiple potential reasons for missed appointments.

## Business Recommendations
- Introduce additional reminders for appointments booked well in advance.
- Prioritise high-risk appointments for confirmation calls or follow-ups.
- Monitor clinics and lead-time groups with higher no-show rates.
- Review patient feedback to understand common reasons for missed appointments.

## Limitations
- The dataset contains 990 appointments across 8 clinics.
- The GenAI analysis uses a small sample of 10 follow-up notes.
- Model predictions are based on historical data and may not generalise to every clinic.
- GenAI-generated classifications should be reviewed by humans.
- Observed patterns do not establish causal relationships.

## Project Structure
```text
CareLoop_Clinic_Project/
│
├── CareLoop_Complete_Analysis.ipynb
├── CareLoop_SQL_Analysis.sql
├── appointments_clean.csv
├── clinics_enriched.csv
├── notes_analysed.csv
├── careloop_genai_merged.csv
├── CareLoop_test_risk_scores.csv
├── comparison_results.csv
└── README.md
```

## How to Run
1. Clone or download this repository.
2. Install the required Python libraries.
3. Open `CareLoop_Complete_Analysis.ipynb` in Google Colab or Jupyter Notebook.
4. Upload the required CSV files.
5. Run the notebook cells in order.
6. For the GenAI section, configure your own Gemini API key securely. Never hardcode or upload API keys.

## Conclusion
This project demonstrates an end-to-end approach to appointment no-show analysis by combining data cleaning, SQL analytics, machine learning, and Generative AI. It aims to help clinics identify potential no-show risks and make better operational decisions.