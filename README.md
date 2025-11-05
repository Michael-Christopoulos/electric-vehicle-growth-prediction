# Electric Vehicle Growth Prediction

This project predicts **which geographic areas are most likely to see growth in electric vehicle (EV) adoption** using open EV registration data and machine learning models.  
It includes data cleaning, model training, and visualizations to highlight the top areas by predicted growth likelihood.

---

## Project Structure

electric-vehicle-growth-prediction/
│
├── data/ # Raw and cleaned datasets
├── figures/ # Saved visualizations (.png)
├── models/ # Trained model files (.joblib)
├── notebooks/ # Jupyter notebooks for each stage
│ ├── 01_data_cleaning.ipynb
│ ├── 02_modeling_visuals.ipynb
│ └── 03_visualizations.ipynb
│
├── README.md # Project documentation
└── gitignore # Ignored files for GitHub

---

## Workflow Overview

### Data Cleaning (`01_data_cleaning.ipynb`)
- Loads EV registration data.
- Handles missing values and removes unnecessary columns.
- Aggregates vehicles by census tract to create area-level metrics.
- Saves output as `cleaned_ev_area_data.csv`.

### Modeling & Visuals (`02_modeling_visuals.ipynb`)
- Scales numeric features.
- Trains **Logistic Regression** and **Random Forest** classifiers.
- Evaluates models using **accuracy, ROC AUC, confusion matrix, and classification report**.
- Random Forest achieved the best performance (~82% accuracy, ROC AUC 0.93).
- Saves the trained model (`random_forest_growth_model.joblib`).

### Visualizations (`03_visualizations.ipynb`)
- Loads predictions and generates clean plots using Matplotlib:
  - Top growth tracts by likelihood.
  - Feature importance chart.
  - ROC curve comparison (if applicable).
- Saves output images to the `figures/` folder.

---

## Example Outputs
- **`figures/feature_importance.png`** — shows which variables most influence EV adoption growth.
- **`figures/top_growth_tracts.png`** — highlights areas ranked by predicted growth.

---

## Key Insights
- **Model year, range, and % of BEVs** are strong predictors of growth.
- Random Forest captures non-linear relationships and performs well on mixed features.
- Areas with newer, longer-range vehicles tend to see higher adoption potential.

---

## Tech Stack
- **Python 3.10+**
- **Libraries:** pandas, numpy, matplotlib, scikit-learn, joblib
- **Environment:** JupyterLab or VS Code

---

## How to Reproduce
1. Clone this repository:
   ```bash
   git clone https://github.com/Michael-Christopoulos/electric-vehicle-growth-prediction.git
   cd electric-vehicle-growth-prediction
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the notebooks in order:
   - `01_data_cleaning.ipynb`
   - `02_modeling_visuals.ipynb`
   - `03_visualizations.ipynb`

---

## License
This project is released under the MIT License — feel free to use and adapt with credit.

---

## 📊 Dataset Source

The dataset used in this project was obtained from [Kaggle](https://www.kaggle.com/), titled **“Electric Vehicle Population Data”**, which aggregates VIN-level electric vehicle registrations and attributes for analysis.

---

**Author:** Michael Christopoulos 
**Project Goal:** Identify U.S. regions most likely to grow in EV adoption using machine learning.
