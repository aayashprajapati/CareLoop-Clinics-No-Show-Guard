# CareLoop Clinics – No-Show Guard

## Project Overview
CareLoop Clinics – No-Show Guard is a data analytics and machine learning project designed to analyse patient appointment no-shows and identify appointments with a higher risk of being missed.

The project combines data cleaning, SQL analysis, machine learning, and Generative AI to generate useful insights and support better appointment management.

## Technologies Used
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- SQL / MySQL
- Gemini API
- Pydantic
- Google Colab

## Project Structure

```text
CareLoop-Clinics-No-Show-Guard/
│
├── data/
│   ├── appointments.csv
│   ├── clinics.csv
│   └── followup_notes.csv
│
├── 01_ingest_clean.ipynb
├── rejected_rows.json
├── appointments_clean.csv
├── clinics_enriched.csv
│
├── load_data.sql
├── 02_queries.sql
│
├── 03_model.ipynb
├── test_risk_scores.csv
│
├── 04_genai.ipynb
├── notes_analysed.csv
├── prompt_comparison.csv
│
└── README.md
```

## Project Workflow

### 1. Data Ingestion and Cleaning
- Loaded and inspected appointment, clinic, and follow-up note datasets.
- Handled missing values, duplicate records, and invalid data.
- Performed data validation and outlier treatment.
- Generated cleaned datasets and enriched clinic information.

### 2. SQL Analysis
- Loaded cleaned datasets into MySQL.
- Performed appointment-level and clinic-level analysis.
- Analysed no-show rates, lead-time patterns, and monthly trends.
- Used SQL aggregations, joins, and ranking functions.

### 3. Machine Learning
- Performed feature preparation and model training.
- Evaluated Logistic Regression, Decision Tree, and Random Forest.
- Compared models using classification metrics and ROC-AUC.
- Selected Logistic Regression and evaluated a threshold of 0.35.
- Generated appointment risk scores.

### 4. Generative AI Analysis
- Used Gemini API to analyse patient follow-up notes.
- Implemented structured outputs using Pydantic.
- Identified possible reasons behind missed appointments.
- Compared two prompt versions to evaluate output consistency.
- Combined AI-generated insights with appointment data.

## Key Results

- Processed 1,020 original appointment records.
- Retained 990 records after cleaning and duplicate removal.
- Observed an overall no-show rate of approximately 22%.
- Achieved 0.7889 ROC-AUC with the selected Logistic Regression model.
- Generated structured root-cause insights from follow-up notes.

## How to Run

1. Clone this repository.
2. Install the required Python libraries.
3. Open the notebooks using Google Colab or Jupyter Notebook.
4. Execute the notebooks in the project workflow order.
5. Configure your Gemini API key securely when running the GenAI notebook.

**Note:** Never share or commit your actual API key.

## Conclusion

This project demonstrates an end-to-end approach to appointment no-show analysis using data analytics, SQL, machine learning, and Generative AI. It aims to help clinics understand no-show patterns and identify potentially high-risk appointments.
