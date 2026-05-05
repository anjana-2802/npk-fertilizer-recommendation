# 🌱 N-P-K Fertilizer Utilization Recommendation System

> A machine learning-based system that predicts optimal Nitrogen, Phosphorus, and Potassium (NPK) fertilizer quantities for Indian farming conditions — deployed as an interactive Gradio web application.

---

## 📌 Project Overview

This project was developed as part of an **internship at PanApps International Pvt. Ltd.** and submitted to **Cochin University of Science and Technology (CUSAT)** in partial fulfillment of the degree of Bachelor of Vocation in Business Process and Data Analytics.

The system addresses a critical agricultural problem: farmers in India typically apply fertilizers based on habit or generalized advice rather than scientific soil assessment. This leads to nutrient imbalances, reduced crop yields, increased costs, and environmental damage from over-application.

The solution is a data-driven recommendation system that takes soil parameters, crop type, and environmental conditions as inputs and predicts the right NPK quantities — along with commercial fertilizer doses (Urea, DAP) and estimated costs.

---

## 🏢 Organization

**PanApps International Pvt. Ltd.**
R&D Division | Kochi, Kerala


PanApps is a technology firm specializing in Cloud Application Software, AI/ML solutions, and enterprise digital transformation. The internship was conducted in their R&D division from December 2025 to April 2026.

---

## 🎯 Objectives

- Analyze soil health metadata and environmental parameters (N, P, K, pH, crop type, location) to identify nutrient deficiency patterns
- Build a multi-output regression model to predict optimal NPK quantities simultaneously
- Compare multiple ML models and select the best performer based on evaluation metrics
- Deploy a functional web interface that translates predicted nutrient values into actionable commercial fertilizer doses

---

## 📂 Repository Contents

| File | Description |
|---|---|
| `code.html` | Complete html file with EDA, preprocessing, modeling, and evaluation |
| `fertilizer_utilization_dataset.csv` | Dataset with 11,256 farm records and 27 attributes |
| `NPK_Fertilizer_recommendation_system.pdf` | Full internship project report |

---

## 📊 Dataset

- **Source:** Provided by project mentors at PanApps International Pvt. Ltd.
- **Size:** 11,256 records × 27 attributes
- **Type:** Structured tabular data representing agricultural conditions across 10 Indian states

### Key Features

| Category | Features |
|---|---|
| Farm & Location | FarmID, State, District |
| Crop & Cultivation | Crop, Season, Farm Size, Years of Cultivation, Previous Yield |
| Soil Parameters | Soil N, P, K (kg/ha), Soil pH, Organic Carbon, Sulphur, Zinc, Electrical Conductivity |
| Environmental | Temperature, Humidity, Rainfall |
| Irrigation | Irrigation Type |
| **Target Variables** | **NPK Recommendation (kg/acre)** |

---

## 🔬 Methodology

This project followed the **CRISP-DM** (Cross-Industry Standard Process for Data Mining) framework across 6 phases:

```
Business Understanding → Data Understanding → Data Preparation
       → Modeling → Evaluation → Deployment
```

### Data Preprocessing
- Missing values in numerical features (Electrical Conductivity, Humidity) imputed using **median** to avoid skew
- Categorical features (State, Crop, Season, Soil Type, Irrigation Type) encoded using **One-Hot Encoding** (`pd.get_dummies`, `drop_first=True`)
- Dataset split **80:20** (train:test) with fixed random state for reproducibility
- Features normalized using **StandardScaler** (mean=0, std=1)

---

## 🤖 Models Used

| Model | Role | Avg R² Score |
|---|---|---|
| Linear Regression | Baseline model | 0.749 |
| Random Forest Regressor | Ensemble — bagging | 0.868 |
| **Gradient Boosting Regressor** | **Best model — sequential boosting** | **0.877** |

All models were implemented using **MultiOutputRegressor** to predict N, P, and K simultaneously.

---

## 📈 Model Performance

| Model | Avg R² | MAE | RMSE |
|---|---|---|---|
| Linear Regression | 0.749 | 5.69 | 7.83 |
| Random Forest | 0.868 | 3.65 | 5.54 |
| **Gradient Boosting** | **0.877** | **3.58** | **5.36** |

**Gradient Boosting** was selected as the final model due to its highest R² score and lowest error values across all three nutrient predictions (N, P, K).

### Top Features by Importance
1. Soil Phosphorus (kg/ha)
2. Previous Yield (kg/acre)
3. Soil Potassium (kg/ha)
4. Soil Nitrogen (kg/ha)
5. Crop type (Groundnut, Sugarcane, Potato)

---

## 🚀 Deployment

The trained model was deployed as an interactive web application using **Gradio**.

### How It Works
1. User inputs: State, Crop, Season, Soil Type, Irrigation Type, Soil N/P/K levels, Farm Size, Previous Yield
2. Non-critical parameters (pH, temperature, rainfall) are auto-filled using dataset medians
3. Model predicts N, P, K recommendations in kg/acre
4. Output includes: nutrient doses, N:P:K ratio, agronomic guidance, and estimated fertilizer cost (Urea/DAP/MOP)

### Quick Example
For **Wheat in Punjab (Rabi season, Clay soil, Drip irrigation)**:
- Nitrogen: 22.3 kg/acre
- Phosphorus: 13.0 kg/acre
- Potassium: 6.3 kg/acre
- N:P:K Ratio → 22:13:6
- Estimated Cost: ₹1,054/acre

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Python** | Core language |
| **Pandas / NumPy** | Data manipulation |
| **Matplotlib / Seaborn** | EDA and visualization |
| **Scikit-learn** | Preprocessing, modeling, evaluation |
| **XGBoost** | Gradient boosting implementation |
| **Gradio** | Web interface deployment |
| **Joblib / Pickle** | Model serialization |
| **Jupyter Notebook** | Development environment |

---

## ⚙️ How to Run

1. Clone the repository:
```bash
git clone https://github.com/anjana-2802/npk-fertilizer-recommendation.git
cd npk-fertilizer-recommendation
```

---

## 📦 Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
gradio
joblib
jupyter
```

---

## 🔮 Future Scope

- Integrate real-time IoT-based soil sensors and weather APIs for dynamic recommendations
- Expand to include crop yield prediction and disease detection
- Develop a mobile application for farmer accessibility
- Incorporate regional government fertilizer guidelines

---

## 👩‍💻 Author

**Anjana Babu**
B.Voc in Business Process and Data Analytics — CUSAT
Internship at PanApps International Pvt. Ltd. (Dec 2025 – Apr 2026)
🔗 [LinkedIn](https://www.linkedin.com/in/anjana-babu-79911b2aa)
🐙 [GitHub](https://github.com/anjana-2802)

---

## 📌 Topics

`python` `machine-learning` `gradient-boosting` `random-forest` `regression` `fertilizer-recommendation` `precision-agriculture` `npk` `gradio` `crisp-dm` `scikit-learn` `jupyter-notebook` 
