# 🤖 AI-Based Product Recommendation & Analytics System

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-FF4B4B?logo=streamlit)](https://streamlit.io)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?logo=scikit-learn)](https://scikit-learn.org)
[![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00?logo=googlecolab)](https://colab.research.google.com)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

---

## 📌 Project Overview

This project develops an **AI-powered product recommendation system** that analyses historical user data — including ratings, purchase history, browsing behaviour, and product attributes — to generate personalised product suggestions.

Unlike basic projects that use a single algorithm, this system implements **4 distinct ML techniques** and combines them into a **Hybrid Engine** for superior recommendation accuracy. An interactive **Streamlit dashboard** with 5 tabs provides real-time analytics and recommendations.

---

## 🎯 Key Features

- ✅ **4 Recommendation Engines** — Content-Based, Collaborative Filtering, SVD, Hybrid
- ✅ **12 EDA Charts** — User demographics, product trends, rating analysis, purchase funnels
- ✅ **SVD Matrix Factorisation** — 20 latent factors, RMSE evaluated on held-out data
- ✅ **Hybrid Engine** — Weighted blend of Collaborative (60%) + Content-Based (40%)
- ✅ **5-Tab Streamlit Dashboard** — Recommendations, Analytics, Products, Users, Model Insights
- ✅ **Live Deployment** — Google Colab + ngrok public URL
- ✅ **No external API** — Fully self-contained, dataset uploaded via Colab

---

## 📁 Repository Structure

```
ai-product-recommendation/
│
├── project.py                          # Main Colab notebook (all cells)
├── Product_Recommendation_Dataset.xlsx # Dataset (3 sheets)
├── requirements.txt                    # Python dependencies
├── README.md                           # This file
│
├── charts/                             # Generated EDA charts (12 PNGs)
│   ├── 01_user_demographics.png
│   ├── 02_product_overview.png
│   ├── 03_user_behaviour.png
│   ├── 04_rating_analysis.png
│   ├── 05_monthly_trend.png
│   ├── 06_top_products.png
│   ├── 07_membership_analysis.png
│   ├── 08_price_discount_insights.png
│   ├── 09_interaction_heatmap.png
│   ├── 10_category_correlation.png
│   ├── 11_svd_evaluation.png
│   └── 12_purchase_funnel.png
│
└── docs/
    └── project_report.pdf              # Full internship report (optional)
```

---

## 📊 Dataset

The dataset is an Excel file with **3 sheets**:

| Sheet | Rows | Columns | Description |
|-------|------|---------|-------------|
| **Users** | 500 | 6 | User_ID, Age, Gender, Location, Membership, Join_Date |
| **Products** | 60 | 12 | Product_ID, Name, Category, Brand, Price, Discount, Rating, Reviews |
| **Interactions** | 8,000 | 9 | User_ID, Product_ID, Rating, Action, Device, Date, Purchased |

**6 Product Categories:** Electronics · Clothing · Books · Home & Kitchen · Sports · Beauty

---

## 🧠 Recommendation Engines

| # | Engine | Technique | Input | Cold Start |
|---|--------|-----------|-------|-----------|
| 1 | **Content-Based** | Cosine Similarity | Product features | ✅ Works |
| 2 | **Collaborative Filtering** | User-User CF | User ratings | ❌ Needs history |
| 3 | **SVD** | Matrix Factorisation | User-Item matrix | ❌ Needs history |
| 4 | **Hybrid** | Weighted Blend (60/40) | Both | ⚠️ Partial |

### SVD Model Evaluation
```
RMSE on known ratings : ~0.82
Explained Variance    : ~0.68 (20 latent components)
User-Item Matrix Shape: 495 × 60
```

---

## 🚀 How to Run

### Option A — Google Colab (Recommended)

1. Open [Google Colab](https://colab.research.google.com)
2. Upload `project.py`
3. Run **Cell 1** — installs all dependencies
4. Run **Cell 2** — imports libraries
5. Run **Cell 3** — upload `Product_Recommendation_Dataset.xlsx` when prompted
6. Run **Cells 4–9** — preprocessing, EDA, model training
7. Run **Cell 10** — writes `app.py`
8. Run **Cell 11** — launches Streamlit (add your ngrok token first)

```python
# In Cell 11, replace with your free token from dashboard.ngrok.com
NGROK_TOKEN = "YOUR_NGROK_TOKEN_HERE"
```

### Option B — Local Machine

```bash
# Step 1: Install dependencies
pip install -r requirements.txt

# Step 2: Run the notebook cells manually, OR run streamlit directly
streamlit run app.py
```

> **Note:** For local run, comment out the `from google.colab import files` import and replace `files.upload()` with direct `pd.read_excel("Product_Recommendation_Dataset.xlsx")`.

---

## 📱 Streamlit Dashboard Tabs

| Tab | What it shows |
|-----|--------------|
| 🎯 **Recommendations** | Select a user → choose engine → get personalised product cards |
| 📊 **Analytics** | Monthly trends, action types, purchases by category, rating distribution |
| 📦 **Products** | Filterable product catalogue, avg price by category, top reviewed |
| 👤 **Users** | Age distribution, city breakdown, membership analysis, purchase rates |
| 🔬 **Model Insights** | SVD explained variance, engine comparison table, rating heatmap |

---

## 🛠️ Tech Stack

```
Language    : Python 3.8+
ML Library  : scikit-learn (SVD, Cosine Similarity, LabelEncoder, MinMaxScaler)
Data        : Pandas, NumPy, SciPy (sparse matrices)
Visualisation: Matplotlib, Seaborn
Web App     : Streamlit
Deployment  : Google Colab + pyngrok
Dataset     : openpyxl (Excel reading)
```

---

## 📦 Installation

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy streamlit pyngrok openpyxl
```

Or use the requirements file:

```bash
pip install -r requirements.txt
```

---

## 📈 Results

- **Content-Based Engine** — recommends by product feature similarity (cosine score)
- **Collaborative Engine** — recommends based on similar user behaviour
- **SVD Engine** — discovers hidden user preference patterns via matrix factorisation
- **Hybrid Engine** — best overall accuracy by blending collaborative + content signals

---

## 🏢 About the Internship

| Field | Details |
|-------|---------|
| Company | Inventeron Technologies and Business Solutions LLP |
| Location | Bangalore, Karnataka |
| Role | Data Analyst Intern |
| Duration | 15 Weeks |
| Domain | Data Science & Machine Learning |
| University | Visvesvaraya Technological University, Belagavi |

**Inventeron Technologies** (est. 2013) provides engineering solutions in AI, Data Science, IoT, Embedded Systems, and EV Technologies. Clients include Indian Army, Indian Air Force, and various SMEs.

---

## ⚠️ Important Notes

- **Never upload your ngrok token** to GitHub. Always use `"YOUR_NGROK_TOKEN_HERE"` as placeholder.
- The dataset is synthetic (generated for academic purposes) — not real customer data.
- Colab sessions reset — re-run all cells if the session expires.

---

## 📄 License

This project is submitted as part of the Bachelor of Engineering internship requirement at VTU, Belagavi.  
For academic use only.

---

## 👥 Authors

| Name | USN | Branch |
|------|-----|--------|
| Student Name | USN Here | Computer Science & Design |

---

*Carried out at **Inventeron Technologies and Business Solutions LLP** under the guidance of Mohammed Atha H K, Chief Technical Officer.*
