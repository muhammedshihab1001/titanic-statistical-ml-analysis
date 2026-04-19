# Titanic Survival Prediction: Statistical Analysis & Machine Learning
![Python](https://img.shields.io/badge/python-3.7+-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Contributions](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)

A comprehensive data science project that combines statistical hypothesis testing with machine learning to predict Titanic passenger survival. This project demonstrates the application of statistical methods for feature selection and validates machine learning model performance through rigorous statistical testing.

## 🎯 Project Overview

This project goes beyond traditional machine learning by integrating **statistical inference** into the model development pipeline. It showcases:

- **Statistical Foundations**: Probability theory, distributions, and descriptive statistics
- **Hypothesis Testing**: Chi-Square tests and Independent T-tests for feature validation
- **Feature Selection**: Data-driven approach using statistical significance (α=0.05)
- **Machine Learning**: Logistic Regression and Random Forest classification
- **Model Validation**: Comprehensive evaluation with paired statistical comparison


## 📊 Dataset

- **Source**: Titanic Dataset (`titanic_toy.csv`)
- **Target Variable**: `Survived` (0 = No, 1 = Yes)
- **Features Used**:
  - `Age`: Passenger age (imputed with median)
  - `Fare`: Ticket fare (imputed with median)
  - `Family`: Family size aboard

## 🗂️ Project Structure

### 1. Import Required Libraries
- Data manipulation: `pandas`, `numpy`
- Statistical analysis: `scipy.stats`
- Machine learning: `scikit-learn`
- Visualization: `matplotlib`, `seaborn`

### 2. Data Loading and Preprocessing
- Load Titanic dataset
- Handle missing values using median imputation
- Define features and target variable
- Perform 80-20 train-test split

### 3. Probability Theory - Bayes' Theorem Example
- Demonstrate conditional probability
- Apply Bayes' Theorem for probability calculations

### 4. Probability Distributions - Normal Distribution Visualization
- Simulate normal distribution (μ=50, σ=10, n=1000)
- Visualize with histogram and KDE overlay

### 5. Descriptive Statistics - Age Analysis
- **Central Tendency**: Mean (29.36), Median (28.0), Mode (28.0)
- **Dispersion**: Range (79.58), Variance (169.51), Std Dev (13.02)

### 6. Distribution Shape Analysis - Skewness and Kurtosis
- **Skewness**: 0.509 (right-skewed distribution)
- **Kurtosis**: 0.982 (leptokurtic, heavier tails)

### 7. Feature Distribution Visualization
- Age distribution: Histogram with KDE
- Fare distribution: Box plot revealing outliers

### 8. Statistical Inference - Confidence Interval Calculation
- 95% Confidence Interval for population mean
- Applied to simulated normal distribution

### 9. Hypothesis Testing - Chi-Square Test for Independence
- **Test**: Family vs Survived
- **Result**: χ²=80.67, p=3.58e-14 ✅ **Highly Significant**
- **Conclusion**: Family size significantly affects survival

### 10. Hypothesis Testing - Independent T-Tests
- **Age vs Survived**: t=-1.90, p=0.058 ⚠️ Not significant
- **Fare vs Survived**: t=6.66, p=8.36e-11 ✅ **Highly Significant**
- **Conclusion**: Fare is a strong predictor, Age is not

### 11. Feature Selection Based on Statistical Testing
- **Selected Features**: Family and Fare (p < 0.001)
- **Dropped Feature**: Age (p > 0.05)
- Re-split data with statistically significant features only

### 12. Model Training - Logistic Regression
- Train baseline linear classifier
- Generate predictions on test set

### 13. Model Training - Random Forest Classifier
- Train ensemble classifier
- Generate predictions for comparison

### 14. Model Evaluation and Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| **Logistic Regression** | 65.36% | 77.27% | 22.97% | 35.42% |
| **Random Forest** | **67.04%** | 62.71% | **50.00%** | **55.64%** |

**Winner**: Random Forest (better balanced performance)

### 15. Statistical Model Comparison - Paired T-Test
- **Test**: Compare predicted probabilities between models
- **Result**: t=-0.498, p=0.619
- **Conclusion**: No significant difference in prediction confidence

## 🔑 Key Findings

1. **Feature Importance** (Validated by Statistical Tests):
   - ✅ **Fare**: Strong predictor (p < 0.001) - Higher fare = Higher survival
   - ✅ **Family**: Strong predictor (p < 0.001) - Family size affects survival
   - ❌ **Age**: Weak predictor (p = 0.058) - Not statistically significant

2. **Model Performance**:
   - Random Forest outperforms Logistic Regression
   - RF achieves better recall (50% vs 23%) - crucial for survival prediction
   - Both models show similar prediction confidence (paired t-test p=0.619)

3. **Statistical Insights**:
   - Age distribution is right-skewed (more younger passengers)
   - Fare has extreme outliers (first-class passengers)
   - Statistical testing effectively guided feature selection

## 🛠️ Technologies Used

**Programming Language:**
- Python 3.x

**Libraries:**
- **Data Manipulation**: `pandas`, `numpy`
- **Statistical Analysis**: `scipy.stats` (chi2_contingency, ttest_ind, norm, f_oneway, skew, kurtosis)
- **Machine Learning**: `scikit-learn` (LogisticRegression, RandomForestClassifier, SimpleImputer)
- **Evaluation Metrics**: `accuracy_score`, `precision_score`, `recall_score`, `f1_score`
- **Visualization**: `matplotlib`, `seaborn`

## 📥 Installation

### Prerequisites
```bash
Python 3.7+
pip package manager
```

### Clone Repository
```bash
git clone https://github.com/muhammedshihab1001/titanic-statistical-ml-analysis.git
cd titanic-statistical-ml-analysis
```

### Install Dependencies
```bash
pip install pandas numpy scikit-learn scipy matplotlib seaborn
```

Or use requirements.txt:
```bash
pip install -r requirements.txt
```

## 🚀 Usage

### Running the Notebook
```bash
Titanic Survival Prediction notebook
# Open the .ipynb file and run all cells
```

### Expected Output
- Statistical test results with p-values
- Distribution visualizations (histograms, box plots, KDE)
- Model performance comparison table
- Feature importance insights

## 📁 File Structure
```
titanic-statistical-ml-analysis/
│
├── dataset/
│   └── titanic_toy.csv           # Titanic dataset
│
├── Titanic Survival Prediction.ipynb                 # Main Jupyter notebook
├── README.md                      # Project documentation
└── requirements.txt               # Python dependencies
```

## 📈 Results Summary

**Best Model**: Random Forest Classifier
- **Accuracy**: 67.04%
- **Precision**: 62.71%
- **Recall**: 50.00%
- **F1-Score**: 55.64%

**Feature Selection Strategy**: Statistical hypothesis testing (α=0.05)
- Retained: Fare, Family
- Removed: Age

**Statistical Validation**: All feature-target relationships validated with p-values < 0.05

## 🎓 Learning Outcomes

This project demonstrates:
- Integration of statistical inference with machine learning
- Data-driven feature selection using hypothesis testing
- Proper handling of missing values
- Model comparison using multiple evaluation metrics
- Statistical validation of model performance differences
- Professional data science workflow: EDA → Testing → Modeling → Evaluation

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👤 Author

**Muhammed Shihab P**

## 🙏 Acknowledgments

- Titanic dataset from Kaggle
- Statistical methods from scipy library
- Machine learning models from scikit-learn

---

**⭐ If you found this project helpful, please give it a star!**