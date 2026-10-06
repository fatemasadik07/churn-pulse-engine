# ✨ ChurnPulse Engine ✨
> *A super chic, end-to-end customer churn prediction & retention engine built for our DEPI capstone project!*

---

## 💖 What is this project all about?

Let's be real: keeping existing customers around is *so* much easier and cheaper than constantly chasing new ones! Most basic churn tools just hand you a random percentage score without explaining **why** someone is thinking of leaving or **whether it's actually worth spending money** on a discount to make them stay.

We built `ChurnPulse Engine` to fix that exact problem with a super smooth, step-by-step workflow:

1. **Spot At-Risk Customers:** Runs clean SQL data pipelines and XGBoost to catch churn patterns early.
2. **Uncover the "Why":** Uses SHAP values so teams can see the exact features pushing a customer away.
3. **Do the Math on Retention:** Balances Customer Lifetime Value ($LTV$), acquisition costs, and special perks so you only spend money saving customers when it actually makes financial sense.
4. **Test "What-If" Scenarios:** Gives stakeholders a cute, interactive dashboard with sliders to test out different retention offers in real time.

---

## 👭 Our Team & Project Roles

We split our repository into 6 clean, focused directories so everyone on the team has total ownership of their own space:

| Directory | Team Role | Lead | What Gets Built Here |
| :--- | :--- | :--- | :--- |
| `core_warehouse/` | Data Engineer | Malak Mostafa | Database tables, SQL scripts, SQLAlchemy setups, and baseline KPI queries. |
| `feature_factory/` | EDA & Preprocessing | Menna Ahmed | Data cleaning, EDA notebooks, missing value fixes, SMOTE balancing, and feature scaling. |
| `intelligence_core/` | ML Specialist | Fatema Sadik | XGBoost/Random Forest models, parameter tuning, cost-matrix math, and SHAP breakdowns. |
| `serving_layer/` | MLOps & API Dev | Rabab Mohamed | Experiment tracking with MLflow, FastAPI routes (`/predict`, `/explain`), and Docker setup. |
| `control_center/` | BI & Dashboard | Youssef El-Kholy | Streamlit app layout, individual customer lookups, and interactive scenario tools. |
| `quality_assurance/`| QA & Integration | Farah Nasser | Pydantic data checks, Pytest test suites, GitHub Actions, and code sanity standards. |

*Built with grit, coffee, and teamwork by 5 girls and 1 guy for our DEPI Capstone!*

---

## 💄 Tech Stack

* **Database:** PostgreSQL / SQLite, SQLAlchemy
* **Data & ML:** Python, Pandas, Scikit-learn, XGBoost, SHAP
* **API & Tracking:** FastAPI, MLflow, Docker
* **Dashboard:** Streamlit, Plotly
* **Testing & Quality Assurance:** Pytest, Pydantic, GitHub Actions

---

## 💅🏽 Getting Started

### 1. Spin up your local environment
```bash
git clone https://github.com/fatemasadik07/churn-pulse-engine.git
cd churn-pulse-engine

python -m venv venv

# On macOS/Linux:
source venv/bin/activate
# On Windows:
venv\Scripts\activate

pip install -r requirements.txt
```
---

## 🎀 How to Run the System

You can run individual components depending on what you are working on, or execute the full pipeline step by step:

### 1. Ingest Data & Set Up Database
Initialize database schemas and seed raw datasets:

```bash
python -m core_warehouse.connectors.db_session
```

### 2. Run Preprocessing & Feature Engineering
Execute the feature pipeline to clean data, encode variables, and transform feature sets:

```bash
python -m feature_factory.pipelines.cleaning
```

### 3. Train ML Models & Generate SHAP Explanations
Train the classifier, evaluate model metrics, and generate SHAP rules:

```bash
python -m intelligence_core.trainers.train_xgboost
```

### 4. Start the FastAPI Serving Layer
Launch the API REST endpoints locally:

```bash
uvicorn serving_layer.app.main:app --reload --port 8000
```
Interactive API docs will be ready for you at `http://localhost:8000/docs`!

### 5. Launch the Streamlit Dashboard
Run the multi-page interface for customer lookups and scenario simulations:

```bash
streamlit run control_center/app.py
```
The dashboard will automatically pop up in your browser at `http://localhost:8501`.

### 6. Run Quality Assurance & Test Suite
Verify data schemas and make sure all test suites pass flawlessly:

```bash
pytest quality_assurance/suite/
```

---

## 📁 DEPI Documentation

All official project planning documentation, requirements, and literature reviews submitted for DEPI evaluation live right inside the `.depi/` folder:

* `01_PROJECT_PLANNING.md`
* `02_REQUIREMENTS_SPECS.md`
* `03_LITERATURE_REVIEW.md`

---

*Made with 💖 by Team ChurnPulse for DEPI.*
