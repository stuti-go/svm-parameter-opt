# Forest Cover Type Classification Using Support Vector Machines (SVM)

## 1. Dataset Summary

- **Dataset Name**: Covertype Dataset  
- **Source**: UCI Machine Learning Repository via `sklearn.datasets.fetch_covtype()`
- **Domain**: Forestry, Remote Sensing, Cartography
- **Number of Instances**: 581,012 (sampled 5,000)
- **Number of Features**: 54  
- **Target Variable**: Forest Cover Type (integer values from 1 to 7 representing different forest categories)

### Feature Overview

The dataset includes:
- Continuous features such as elevation, slope, horizontal/vertical distances to hydrology, roadways, and fire points.
- Binary indicators for 40 soil types and 4 wilderness areas.

---

## 2. Methodology

### 2.1 Preprocessing

- Selected a random subset of 5,000 instances from the dataset to reduce computational overhead.
- Standardized the features using `StandardScaler` to improve model convergence and performance.

### 2.2 Model Training

- Used **Support Vector Classification (SVC)** from scikit-learn.
- Evaluated four SVM kernels: `linear`, `poly`, `rbf`, and `sigmoid`.
- Conducted a random search for hyperparameters `C` (regularization) and `gamma` (kernel coefficient).
- Performed 10 train/test splits (stratified) to evaluate consistency across samples.

### 2.3 Evaluation

- Accuracy was used as the primary evaluation metric.

---

## 3. Results

### 3.1 Accuracy Across Samples

![Results Table](results_table.png)

### 3.2 Learning Curve of Best Performing Model

![Learning Curve](convergence_graph.png)

---

## 4. Observations

- The `poly` kernel frequently produced the best results in this random hyperparameter search.
- The learning curve indicated that model accuracy improved consistently with more data but may plateau, indicating possible bias or limited model capacity with the selected kernel/hyperparameters.

