# Cancer diagnosis with Machine Learning
A machine learning project classifying breast tumors as malignant or benign using the Wisconsin Breast Cancer Dataset. This is a portfolio project to demonstrate end-to-end ML pipeline development.

## Dataset
**Source:** Wisconsin Breast Cancer Dataset (UCI / sklearn)
**Samples:** 569 (357 benign, 212 malignant)
**Features:** In total 30. 10 cell nucleus measurments computed as mean, standard error and worst value.

## Models
Five models trained and compared using 5-fold cross validation:
-Logistic Regression
-Random Forest
-Support Vector Machine (SVM)
-Multi-layer Perceptron (MLP)
-K-Nearest Neighbors (KNN)

## Evaluation Metrics
- **Recall (Sensitivity)** prioritized: missing a cancer case is worse than a "false alarm".
- Precision 
- F1-score
- Accuracy
- AUC-ROC

## Feature Analysis
The 30 features were analysed with respect to their correlation with the target variable using Pearson correlation and KDE plots for the top 5 most diagnostic features.

## Project Structure
cancer-diagnosis-ml/
├── notebooks/
│   ├── 01_EDA.ipynb        # Exploratory data analysis
│   └── 02_modeling.ipynb   # Model training and evaluation
├── src/
├── data/
└── results/

## Results
| Model | Accuracy | Recall | Precision | F1 |
|---|---|---|---|---|
| Logistic Regression | 0.980 | 0.989 | 0.980 | 0.984 |
| MLP | 0.978 | 0.989 | 0.976 | 0.983 |
| SVM | 0.971 | 0.979 | 0.976 | 0.977 |
| KNN | 0.967 | 0.982 | 0.966 | 0.974 |
| Random Forest | 0.954 | 0.968 | 0.959 | 0.963 |

**Best model: Logistic Regression** with recall at 0.9762, AUC 0.995 on test set.

## Key Findings
- Worst-value features dominate. Extreme cell measurements are more diagnostically useful than averages
- Strongest indicators of malignancy: worst concave points, worst perimeter and worst radius.
- Strong correlation between size related features (radius, perimeter, area)
- All models achieved strong performance scores on 5-fold cross-validation with Logistic Regression on top.
- Logistic Regression achieved recall of 0.9762 and AUC 0.995 on test data, 
correctly identifying 41 out of 42 malignant cases

## Tech Stack
- Python 3.11
- scikit-learn, pandas, numpy
- matplotlib, seaborn
- Jupyter Notebook

## How to Run
```bash
git clone https://github.com/mattiasrasander-creator/ML-Cancer-Diagnostic
cd ML-Cancer-Diagnostic
python -m venv venv
source venv/Scripts/activate
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
jupyter notebook
```
