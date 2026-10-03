# ML Assignment 3 — Data Preprocessing: Doing it in the Right Order

**Repository Name**: `ml-assignment-3-preprocessing`  
**Submission Task**: Task 3 (Machine Learning Assignments 1 to 4\)

---

## 1\. Dataset Source Link

- **Dataset**: Adult Census Income Dataset  
- **Source Link**: [UCI Machine Learning Repository — Adult Dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.data)  
- **Description**: Benchmark census dataset containing 32,561 records with mixed numerical and categorical attributes, genuine missing values (represented as '?'), and an imbalanced target (`income` \>50K vs \<=50K).

---

## 2\. Methodology & Leakage Prevention

- **Strict Split Precedence**: Data is split into 80/20 train and test sets stratified on `income` before any preprocessing or fitting occurs.  
- **Leakage Demonstration**: Shows numerical distortion when fitting a scaler on the entire dataset versus strictly fitting on the training set.  
- **Pipeline Architecture**: `ColumnTransformer` with `SimpleImputer`, `RobustScaler`, and `OneHotEncoder(handle_unknown='ignore')`.  
- **Target Imbalance**: SMOTE oversampling applied strictly to the training split.

---

## 3\. Repository Contents

- `assignment3_preprocessing.ipynb`: Executable Colab notebook with all outputs visible.  
- `pipeline.joblib`: Serialized preprocessing pipeline fitted strictly on training data.  
- `README.md`: Dataset source documentation and workflow summary.