# 🧠 Binary Classification: Marketplace Product Matching  
![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)  
![ML Project](https://img.shields.io/badge/Type-Machine%20Learning-green)  
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)  


## 📦 Project Summary  
This project addresses a real-world problem from [Samokat.Tech](https://samokat.tech) — a tech-driven, real-time delivery platform.  
I developed the **final stage of a product matching pipeline**, where the task was to determine whether a seller’s offer matches a catalog product.

It’s a **binary classification problem**, using structured tabular features as well as **image and text embeddings**.

---

## 🧾 About Samokat.Tech  
[Samokat.Tech](https://samokat.tech) powers one of Russia’s most innovative grocery delivery services.  
Their fully automated and digitized supply chain helped them grow from:

- 📦 **1.6M orders/month in 2020**  
- 🚀 **92M orders in H1 2023**  

This rapid growth is driven by advanced **IT systems**, **machine learning**, and **robotics**.

---

## 🧠 Problem Formulation  

**Objective:**  
Predict whether a pair of products — one from a marketplace seller, one from the internal catalog — represent the **same item**.

- 🔍 **Match** (`1`)  
- ❌ **No Match** (`0`)  

Each product pair included:
- Tabular attributes
- Image embeddings
- Text embeddings

**Evaluation Metric:**  
F1-Score

---

## 📊 Dataset Overview  

Data was provided by [Megamarket](https://megamarket.ru/) and includes:

### 📁 Files
- `train.csv` — Labeled training data  
- `test.csv` — Testing data for evaluation

### 🔑 Key Columns  
| Column | Description |
|--------|-------------|
| `offer_depersonalised`, `goods_depersonalised` | IDs of the seller offer and product |
| `attrs+title_score` | Pre-scored match likelihood |
| `sum_length` | Combined length of names & attributes |
| `offer_price`, `item_price` | Prices for each item |
| `target` | Binary match label (in train.csv only) |

### 🔎 Embeddings  
- Image vectors: `goods_image_vectors`, `offer_image_vectors`  
- Title/text vectors: `goods_title_vectors`, `offer_title_vectors`

---

## 🔨 Tech Stack & Tools  

| Category        | Tools / Libraries                    |
|----------------|---------------------------------------|
| Language        | Python 3.10                          |
| ML Libraries    | CatBoost, LightGBM, Scikit-learn     |
| Data Handling   | Pandas, NumPy                        |
| Embedding Work  | PCA, Distance Metrics                |
| Notebooks       | Jupyter                              |

---

## 🚀 Project Workflow

- ✅ Cleaned & analyzed tabular + embedding data  
- 🔍 Calculated **image/text embedding distances**  
- 📉 Used **PCA** to reduce vector dimensionality  
- ➕ Engineered features like **price differences**  
- 🔁 Built multiple ML models (CatBoost, LGBM, etc.)  
- 🧠 Stacked predictions using a **Naive Bayes meta-model**  
- ⚡ Final model: **CatBoost** (best performance + fastest)

---

## 🏁 Results

| Model         | F1 Score | Notes                        |
|---------------|----------|------------------------------|
| CatBoost      | ✅ Best   | Fast + Accurate              |
| Meta-Model    | Slightly higher | Slower, less efficient     |
| LGBM, Others  | Good     | Used in stacking             |

📌 **Recommendation:** Use **CatBoost** for production deployment.



