# Alphabet Soup Charity Model Report

## 🧠 Overview of the Analysis
The objective of this project is to develop a deep learning model that can predict whether a nonprofit organization will be successful in securing funding.

We used historical application data and built two deep learning models:
- An initial baseline model
- An optimized model using tuning strategies

---

## 📊 Results

### 🔹 Data Preprocessing
- **Target Variable:** `IS_SUCCESSFUL`
- **Dropped Columns:** `EIN`, `NAME`
- **Categorical Encoding:** `pd.get_dummies()`
- **Feature Scaling:** `StandardScaler`

### 🔹 Initial Model
- **Layers:** 2 hidden layers (80 and 30 nodes)
- **Activations:** ReLU
- **Epochs:** 50
- **Accuracy:** 72.5%

### 🔹 Optimized Model
- **Layers:** 3 hidden layers (80, 64, 30 nodes)
- **Activations:** `tanh`, `relu`
- **Dropout:** 0.2 added after first layer
- **Epochs:** 100
- **Batch Size:** 64
- **Accuracy:** 78.1%

---

## 📈 Model Evaluation & Analysis

### ❓ What features were selected as inputs?
All columns after preprocessing were used, excluding the target column (`IS_SUCCESSFUL`). These included encoded categorical features and scaled numerical ones.

### ❓ What variable was the target?
`IS_SUCCESSFUL` – a binary variable indicating whether the nonprofit received funding.

### ❓ What are the performance metrics of your model?
- **Initial Model Accuracy:** 72.5%
- **Optimized Model Accuracy:** 78.1%
- The optimized model showed stronger generalization based on validation accuracy.

### ❓ What steps were taken to optimize the model?
- Increased number of hidden layers and neurons
- Changed activation function from ReLU to `tanh` in the first layer
- Added `Dropout()` to reduce overfitting
- Increased epochs and adjusted batch size

### ❓ What is the final accuracy of your optimized model?
**78.1%** on the test set.

### ❓ Could another model type perform better? Why or why not?
Yes. A **Random Forest Classifier** or **XGBoost** model might perform better on this structured, tabular data. These models naturally handle categorical variables, require less preprocessing, and can capture complex interactions without deep architectures.

---

## 📂 Files in This Project
- `Starter_Code.ipynb` → Initial model notebook
- `AlphabetSoupCharity.keras` → Initial model file
- `AlphabetSoupCharity_Optimization.ipynb` → Optimized model notebook
- `AlphabetSoupCharity_Optimization.h5` → Optimized model file
- `report-template.md` → Final report

---

## 🧾 Final Thoughts
The optimized neural network showed a meaningful improvement in prediction accuracy. With additional tuning or by exploring tree-based models, the performance could likely be improved further.
