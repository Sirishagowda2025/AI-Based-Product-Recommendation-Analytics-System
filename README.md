# 🤖 AI-Based Product Recommendation & Analytics System

An intelligent recommendation system that analyses user behaviour, purchase history, and product attributes to deliver personalised product suggestions using **4 ML algorithms** combined into a Hybrid Engine — deployed as a live interactive web dashboard.

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-FF4B4B?logo=streamlit&logoColor=white)](https://streamlit.io)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Pandas](https://img.shields.io/badge/Pandas-Data-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## ✨ What it does

- Recommends products to users based on past interactions, ratings, and browsing behaviour
- Implements **4 different ML recommendation techniques** and combines them for best accuracy
- Provides a full **analytics dashboard** with charts on user behaviour, product trends, and purchase patterns
- Deployed as a **live Streamlit web app** — no code knowledge needed to use it

---

## 🧠 Recommendation Engines

| Engine | Technique | How it works | Best for |
|--------|-----------|-------------|----------|
| **Content-Based** | Cosine Similarity | Recommends products similar in features (category, brand, price, rating) | New users |
| **Collaborative Filtering** | User-User CF | Finds users with similar taste and recommends what they liked | Active users |
| **SVD** | Matrix Factorisation | Discovers hidden preference patterns via latent factor decomposition | Large datasets |
| **Hybrid** | Weighted Blend 60/40 | Combines Collaborative + Content-Based signals for best accuracy | All users |

### Model Evaluation
```
SVD RMSE on held-out ratings : ~0.82
SVD Explained Variance        : ~0.68  (20 latent components)
User-Item Matrix Shape        : 495 × 60
```

---

## 📊 Dataset

Three-sheet Excel file — **8,560 total records**

| Sheet | Rows | Key Columns |
|-------|------|-------------|
| Users | 500 | User_ID, Age, Gender, City, Membership |
| Products | 60 | Product_ID, Category, Brand, Price, Discount, Rating |
| Interactions | 8,000 | User_ID, Product_ID, Rating, Action, Device, Date |

**6 categories:** Electronics · Clothing · Books · Home & Kitchen · Sports · Beauty

---

## 📈 EDA — 12 Charts

| # | Chart | Insight |
|---|-------|---------|
| 1 | User demographics | Age distribution, gender split |
| 2 | Product catalogue | Price by category, products per category |
| 3 | Interaction behaviour | Action types (view/cart/purchase/wishlist), device split |
| 4 | Rating analysis | Distribution, avg rating per category |
| 5 | Monthly trend | Interaction and purchase trend over time |
| 6 | Top products | Top 10 most interacted products |
| 7 | Membership analysis | Purchase rate by membership tier |
| 8 | Price & discount | Discount vs rating scatter |
| 9 | User-product heatmap | Rating heatmap (top 15 users × top 15 products) |
| 10 | Co-purchase correlation | Category pair correlation from purchase history |
| 11 | SVD evaluation | Explained variance curve |
| 12 | Purchase funnel | Action breakdown by category |

---

## 🖥️ Dashboard — 5 Tabs

| Tab | What it shows |
|-----|--------------|
| 🎯 **Recommendations** | Select any user → pick engine → get personalised product cards with scores |
| 📊 **Analytics** | Monthly trends, action types, purchases by category, rating distribution |
| 📦 **Products** | Filterable product catalogue, avg price by category, most reviewed |
| 👤 **Users** | Age, city, membership, and purchase rate breakdowns |
| 🔬 **Model Insights** | SVD variance curve, engine comparison table, rating heatmap |

---

## 🚀 Quick Start

### Option A — Google Colab

```
1. Open colab.research.google.com
2. Upload project_clean.py
3. Run Cell 1  →  installs all dependencies
4. Run Cell 2  →  imports libraries
5. Run Cell 3  →  upload Product_Recommendation_Dataset.xlsx when prompted
6. Run Cells 4–9  →  preprocessing, EDA, model training
7. Run Cell 10  →  writes app.py
8. Run Cell 11  →  paste ngrok token → get live URL → open in browser
```

> Get a free ngrok token at [dashboard.ngrok.com](https://dashboard.ngrok.com)

### Option B — Local Machine

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Run all cells in project_clean.py first to generate app.py
# 3. Launch the dashboard
streamlit run app.py
```

> For local run: in Cell 3, replace `files.upload()` with `pd.read_excel("Product_Recommendation_Dataset.xlsx")`
> and remove the `from google.colab import files` import line.

---

## ⚙️ How the Hybrid Engine works

```
User interactions
      │
      ├──► Collaborative Filtering (user-user cosine similarity) ──► score_CF
      │
      └──► Content-Based Filtering (product feature cosine sim)  ──► score_CB
                                                                          │
                                    Hybrid Score = 0.6 × score_CF + 0.4 × score_CB
                                                                          │
                                                              Top-N product recommendations
```

---

## 🛠️ Tech Stack

| Layer | Tools |
|-------|-------|
| Language | Python 3.8+ |
| ML & Data | scikit-learn, Pandas, NumPy, SciPy |
| Visualisation | Matplotlib, Seaborn |
| Web App | Streamlit |
| Deployment | pyngrok + Google Colab |
| Dataset | openpyxl (Excel) |

---

## 📂 Project Structure

```
ai-product-recommendation/
│
├── project_clean.py                         ← Main notebook (all cells)
├── Product_Recommendation_Dataset.xlsx      ← Dataset (3 sheets)
├── README.md                                ← This file
├── requirements.txt                         ← pip dependencies
├── .gitignore                               ← Excludes generated files
│
└── charts/                                  ← EDA output (12 PNGs)
    ├── 01_user_demographics.png
    ├── 02_product_overview.png
    ├── 03_user_behaviour.png
    ├── 04_rating_analysis.png
    ├── 05_monthly_trend.png
    ├── 06_top_products.png
    ├── 07_membership_analysis.png
    ├── 08_price_discount_insights.png
    ├── 09_interaction_heatmap.png
    ├── 10_category_correlation.png
    ├── 11_svd_evaluation.png
    └── 12_purchase_funnel.png
```

---

## 📄 License

MIT — free to use, modify, and distribute with attribution.

---

> Built with Python · scikit-learn · Streamlit
