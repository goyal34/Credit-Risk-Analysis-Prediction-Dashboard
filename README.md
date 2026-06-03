💳 Credit Risk Analysis & Default Prediction Dashboard
An end-to-end credit risk pipeline — from raw loan applicant data through SQL-based feature engineering and XGBoost modelling to an interactive Power BI dashboard for real-time loan default monitoring.

📌 Project Overview
Credit default is one of the highest-impact risk problems in fintech and banking. This project builds a full-stack analytics solution that:

Cleans and engineers features from raw loan data using SQL (PostgreSQL)
Trains and evaluates ML models using Python (XGBoost, Random Forest)
Visualises risk exposure and default patterns in an interactive Power BI dashboard


🛠️ Tech Stack
LayerToolsData PreparationSQL (PostgreSQL, pgAdmin4)Machine LearningPython, Pandas, Scikit-learn, XGBoost, Random ForestVisualisationPower BI (DAX, Power Query)Hyperparameter TuningGridSearchCV

🔑 Steps Implemented
1️⃣ Data Preparation (SQL)

Imported loan applicant dataset into PostgreSQL
Cleaned missing values (median imputation for numeric, mode for categorical)
Engineered new features:

Loan-to-Income Ratio — strongest default predictor
Employment Category (binned employment length)
Age Bands, Income Bands, Interest Rate Bands


Verified data distributions and default rates by category using CTEs

2️⃣ Machine Learning (Python)

Encoded categorical variables using OneHotEncoder
Built pipelines with Random Forest and XGBoost
Tuned hyperparameters using GridSearchCV
Key results:

✅ Accuracy: ~93%
✅ Recall (Defaults): ~75% after XGBoost tuning
✅ Top Predictors: Loan-to-Income, Income, Interest Rate, Loan Amount


Generated default probabilities for new applicants (scalable to 5,000+ records at once)

3️⃣ Power BI Dashboard

Built DAX measures:

Default Probability
Actual Loss (observed defaults)
Expected Loss = Exposure × PD × LGD


Interactive slicers: Loan Intent, Loan Grade, Income Range


📊 Key Business Insights
MetricValueGood Loans %78.18%Default Rate22%Total Loan Amount at Risk$77MExpected Loss$68.16MTop Risky PurposeDebt Consolidation (29%)Highest Risk SegmentNew Employees 0–2 yrs (30%)

Higher Loan Grades (F, G) have default rates > 70%
Loan-to-Income ratio and Interest Rate are the strongest predictors of default
XGBoost outperformed Random Forest in recall for the minority (default) class


🚀 How to Run
bash# 1. Clone the repo
git clone https://github.com/goyal34/Credit-Risk-Analysis-Prediction-Dashboard
cd Credit-Risk-Analysis-Prediction-Dashboard

# 2. Install dependencies
pip install -r requirements.txt

# 3. Load SQL scripts in PostgreSQL to clean & prep data

# 4. Run the notebook
jupyter notebook credit_risk_model.ipynb

# 5. Open Power BI file
# Open: Loan Defaulters Final.pbix

📁 Repository Structure
├── credit_risk_dataset.csv          # Raw loan applicant data
├── new_credit_risk_dataset.csv      # Processed dataset
├── credit_risk_model.ipynb          # ML pipeline notebook
├── Loan Defaulters Final.pbix       # Power BI dashboard
├── requirements.txt                 # Python dependencies
└── README.md

🔮 Future Improvements

Deploy ML model as a Flask/FastAPI for real-time scoring
Connect API to Power BI for live scoring dashboards
Add survival analysis for loan tenure risk
Experiment with Neural Networks (TabNet, AutoML)


👤 Author
Aman Goyal
IIT (BHU) Varanasi | B.Tech
LinkedIn | GitHub
