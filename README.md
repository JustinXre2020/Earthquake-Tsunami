# Earthquake Tsunami Prediction Analysis

**DATA1030 Final Project**  
**Student:** Justin Xiao  
**Institution:** Brown University  
**Date:** October 24, 2025  
**GitHub Repository:** [Earthquake-Tsunami](https://github.com/JustinXre2020/Earthquake-Tsunami)

---

## 🚀 How to Run the Analysis

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook or JupyterLab

### Installation Steps

1. **Clone the repository** (if applicable):
   ```bash
   git clone https://github.com/JustinXre2020/Earthquake-Tsunami.git
   cd Earthquake-Tsunami
   ```

2. **Install required packages**:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn xgboost
   ```

3. **Navigate to the project directory**:
   ```bash
   cd /path/to/project
   ```

4. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook src/analysis.ipynb
   ```
   Or use JupyterLab:
   ```bash
   jupyter lab src/analysis.ipynb
   ```

5. **Run all cells** in sequence using `Shift + Enter` or select `Cell > Run All` from the menu.

### Data Requirements
Ensure the following CSV files are in the `data/` directory:
- `earthquake_1995-2023.csv`
- `earthquake_data.csv`

---

## 📊 Project Overview

This project develops a machine learning model to predict tsunami occurrences following earthquakes using seismic and geographic features. Given the critical importance of early warning systems for coastal populations, the goal is to create a reliable classifier that can identify high-risk earthquake events in real-time.

### Key Objectives
- Analyze historical earthquake data to identify tsunami risk patterns
- Build a predictive model using XGBoost with optimized hyperparameters
- Provide interpretable insights through feature importance and SHAP analysis
- Achieve high sensitivity for tsunami detection while maintaining specificity

---

## 📁 Dataset Description

The analysis combines two earthquake datasets covering events from 1995-2023:

**Features (10 predictors):**
- `magnitude`: Earthquake magnitude (Richter scale)
- `depth`: Depth of earthquake hypocenter (km)
- `latitude` / `longitude`: Geographic coordinates
- `cdi`: Community Decimal Intensity
- `mmi`: Modified Mercalli Intensity
- `sig`: Significance score
- `nst`: Number of seismic stations
- `dmin`: Minimum distance to seismic station
- `gap`: Azimuthal gap

**Target Variable:**
- `tsunami`: Binary indicator (1 = tsunami occurred, 0 = no tsunami)

**Class Distribution:** Highly imbalanced (~3% tsunami events)

---

## 🔍 Methodology

### 1. Exploratory Data Analysis (EDA)
- **Magnitude vs Depth Analysis**: Tsunamis predominantly occur with shallow earthquakes (<100 km depth)
- **Geographic Distribution**: Strong clustering in the Pacific Ring of Fire
- **Correlation Analysis**: Key features include magnitude, depth, and geographic location
- **Missing Values**: Comprehensive analysis and handling strategy

### 2. Data Preprocessing
- **Train/Validation/Test Split**: 60% / 20% / 20% stratified split
- **Feature Scaling**: StandardScaler normalization
- **Class Imbalance Handling**: Stratified sampling and `scale_pos_weight` tuning

### 3. Model Development
- **Baseline Model**: Dummy classifier (majority class prediction)
- **Primary Model**: XGBoost Classifier with extensive hyperparameter tuning
- **Cross-Validation**: Stratified 5-fold CV on training set
- **Optimization Metric**: ROC-AUC (appropriate for imbalanced data)

### 4. Hyperparameter Tuning
Grid search over:
- `max_depth`: [3, 5, 7]
- `learning_rate`: [0.01, 0.1, 0.3]
- `n_estimators`: [100, 200, 300]
- `min_child_weight`: [1, 3, 5]
- `subsample`: [0.8, 1.0]
- `colsample_bytree`: [0.8, 1.0]
- `scale_pos_weight`: [1, 10, 30]

---

## 📈 Key Results

### Model Performance (Test Set)
| Metric | Baseline | XGBoost |
|--------|----------|---------|
| **Accuracy** | 0.972 | 0.980 |
| **Precision** | 0.000 | 0.857 |
| **Recall** | 0.000 | 0.857 |
| **F1-Score** | 0.000 | 0.857 |
| **ROC-AUC** | N/A | 0.956 |

### Feature Importance (Top 5)
1. **Depth** - Most critical predictor (shallow earthquakes → higher tsunami risk)
2. **Magnitude** - Strong positive correlation with tsunami occurrence
3. **Latitude** - Geographic location indicator (Pacific rim regions)
4. **Longitude** - Complements latitude for spatial patterns
5. **Significance (sig)** - Composite measure of earthquake impact

### Key Insights
- ✅ **Excellent discrimination**: ROC-AUC > 0.95 demonstrates strong predictive power
- ✅ **High specificity**: Correctly identifies 98%+ of non-tsunami events
- ✅ **Reasonable sensitivity**: Detects 85%+ of actual tsunami events
- ✅ **Interpretable predictions**: SHAP values provide instance-level explanations
- ✅ **Domain alignment**: Important features match seismological knowledge

---

## 📊 Visualizations

The notebook includes comprehensive visualizations:
- **Magnitude vs Depth**: Scatter plot showing tsunami event patterns
- **Geographic Distribution**: World map highlighting Pacific Ring of Fire
- **Correlation Heatmap**: Feature relationships and multicollinearity analysis
- **Confusion Matrix**: Classification performance breakdown
- **ROC Curve**: Trade-off between true/false positive rates
- **Feature Importance**: Global impact of each predictor
- **SHAP Analysis**: Local interpretability for individual predictions
- **Model Comparison**: Baseline vs XGBoost performance across metrics

---

## 🔮 Future Work

### Predictive Power Improvements
- Incorporate fault type and rupture characteristics
- Engineer temporal features for aftershock sequences
- Explore ensemble methods (Random Forest, Neural Networks)
- Implement SMOTE for better class balance
- Develop cost-sensitive learning with custom loss functions

### Interpretability Enhancements
- Generate SHAP force plots for high-risk predictions
- Create interactive dashboards for real-time monitoring
- Extract decision rules from XGBoost trees
- Perform sensitivity analysis on critical features

### Deployment Considerations
- Build real-time prediction pipeline with USGS earthquake feeds
- Establish probability thresholds balancing safety vs false alarms
- Conduct geographic validation across different tectonic regions
- Integrate with existing early warning systems

---

## 🛠️ Technical Stack

- **Data Processing**: pandas, numpy
- **Visualization**: matplotlib, seaborn
- **Machine Learning**: scikit-learn, XGBoost
- **Interpretability**: SHAP values (via XGBoost native implementation)
- **Development**: Jupyter Notebook

---

## 📝 License

This project is part of academic coursework at Brown University (DATA1030).

---

## 🙏 Acknowledgments

- USGS Earthquake Database for providing comprehensive seismic data
- DATA1030 course staff for guidance and support
- Brown University for research resources