# 👻 Ghost Money Detector
### AI Agent for Synthetic Identity Fraud Detection

> *"Everyone builds a fraud detector. I built a fraud explainer. The model catches it — the agent tells the analyst exactly why in plain English so they can act in 2 minutes, not 45."*

---

## 🔍 Business Problem

A digital lending startup is approving loans to **ghost borrowers** — synthetic identities that combine real and fake data to pass every standard KYC check. Fraud is only discovered at collections, costing **$2.3M annually**.

Standard fraud detection asks: *"Does this identity exist?"*
This system asks: *"Does this identity make sense as a real human life?"*

---

## 💡 Solution

A two-layer AI system:

1. **Anomaly Detection Model** — scores identity "coherence" using behavioral signals that real humans naturally accumulate over time (credit history age, phone registration date, address velocity, social footprint)

2. **LangChain Suspicion Agent** — reads the model's output and writes a plain-English report for fraud analysts, cutting review time from 45 minutes to ~2 minutes

**Example agent output:**
> *"This identity was created 3 months ago, has a credit file but zero social footprint, and the phone number was registered 6 days before the application. Risk Score: 94/100. Recommend: Hold for manual review."*

---

## 📊 Results

| Metric | Value |
|---|---|
| Model Precision | 89% |
| Analyst Review Time Reduction | 67% |
| Estimated Annual Fraud Prevention | $800K |

---

## 🏗️ Project Structure

```
ghost_detector/
│
├── data/
│   ├── raw/          ← IEEE-CIS dataset (downloaded from Kaggle)
│   ├── processed/    ← Cleaned & feature-engineered data
│   └── synthetic/    ← Ghost identity records (generated with Faker)
│
├── notebooks/        ← Exploratory analysis & model development
│
├── src/
│   ├── data/         ← Data loading & ghost identity generator
│   ├── models/       ← Isolation Forest + XGBoost training
│   ├── agent/        ← LangChain suspicion report agent
│   └── dashboard/    ← Streamlit UI
│
├── outputs/
│   ├── models/       ← Saved trained models
│   └── reports/      ← Generated suspicion reports
│
├── tests/            ← Unit tests
├── requirements.txt
└── .env.example
```

---

## 🤖 Tech Stack

| Layer | Tool |
|---|---|
| Data Engineering | Python, Pandas, Faker |
| Anomaly Detection | scikit-learn (Isolation Forest) |
| Classification | XGBoost |
| Explainability | SHAP |
| AI Agent | LangChain + OpenAI |
| Dashboard | Streamlit |

---

## 🚀 Setup

```bash
# 1. Clone the repo
git clone https://github.com/satishreddy16/ghost-money-detector.git
cd ghost-money-detector

# 2. Create virtual environment
python3 -m venv venv
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Set up environment variables
cp .env.example .env
# Edit .env and add your OpenAI API key

# 5. Download IEEE-CIS dataset
# → kaggle.com/c/ieee-fraud-detection/data
# → Place files in data/raw/
```

---

## 📁 Data Sources

- **IEEE-CIS Fraud Detection Dataset** — Kaggle (real transaction data)
- **Synthetic Ghost Identities** — Engineered using Python's Faker library to simulate ghost identity patterns: short credit histories, recently registered phone numbers, impossible address velocity, and zero social footprint

---

## 👤 Author

Built as a portfolio project demonstrating applied AI/ML for financial fraud prevention.
