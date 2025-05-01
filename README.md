# Day 5: Decision Trees & Random Forests – Heart Disease Prediction

---

## 🎯 Objective
To build and compare Decision Tree and Random Forest models for predicting the presence of heart disease based on patient attributes. The task involves detecting overfitting, tuning hyperparameters, analyzing feature importance, and validating model performance using cross-validation.

---

## 📁 Dataset
- Dataset used: `heart.csv`
- Total rows: 1,025
- Target: `target` (1 = heart disease, 0 = no heart disease)
- No missing values

---

## 🧠 Models Used

### 1. 🌳 **Decision Tree Classifier**
- Trained using default parameters initially
- Accuracy: **98.5%** (overfitted)
- Controlled overfitting using:
  - `max_depth=4`
  - `min_samples_split=10`
  - `min_samples_leaf=5`
- Pruned accuracy: **83.9%**

### 2. 🌲 **Random Forest Classifier**
- Used ensemble of 100 trees with:
  - `max_depth=5`
  - `min_samples_split=10`
  - `min_samples_leaf=5`
- Accuracy: **92.2%**
- Cross-validation (5-fold):
  - Mean Accuracy: **91.1%**
  - Std Dev: ±0.03
- Great generalization + stability

---

## 🔍 Feature Importance (Top Predictors)

| Feature | Description |
|--------|-------------|
| `cp` | Chest pain type |
| `ca` | Number of major vessels |
| `thal` | Thalassemia |
| `thalach` | Max heart rate achieved |
| `exang` | Exercise-induced angina |

---

## 📊 Evaluation Metrics Used
- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix
- ROC Curve (optional)
- Cross-Validation Score

---

## 📈 Final Model Summary

| Model            | Accuracy | Cross-Val | Overfit |
|------------------|----------|-----------|---------|
| Decision Tree    | 98.5% (unpruned) | —         | 🚨 High |
| Pruned Tree      | 83.9%     | —         | ✅ Low |
| Random Forest ✅ | **92.2%** | **91.1%** | ✅ Robust |

---

## 🛠️ How to Run This Project Locally

```bash
# Clone the repo
git clone https://github.com/your-username/heart-disease-decisiontree-rf.git

cd heart-disease-decisiontree-rf

# Optional: create virtual env
python -m venv venv
venv\Scripts\activate

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn

# Launch notebook
jupyter notebook
