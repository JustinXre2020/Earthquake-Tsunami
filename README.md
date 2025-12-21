# Earthquake Tsunami Prediction Analysis

**DATA1030 Final Project**  
**Student:** Justin Xiao  
**Institution:** Brown University  
**Date:** October 24, 2025  
**GitHub Repository:** [Earthquake-Tsunami](https://github.com/JustinXre2020/Earthquake-Tsunami)

---

## How to Run the Analysis

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

## Project Overview

This project develops machine learning models to predict tsunami occurrences following earthquakes using seismic and geographic features. Given the critical importance of early warning systems for coastal populations, the goal is to create a reliable classifier that can identify high-risk earthquake events in real-time.

### Key Objectives
- Analyze historical earthquake data to identify tsunami risk patterns
- Build a predictive model using XGBoost with optimized hyperparameters
- Provide interpretable insights through feature importance and SHAP analysis
- Achieve high sensitivity for tsunami detection while maintaining specificity
