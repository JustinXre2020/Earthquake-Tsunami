# Earthquake Tsunami Prediction Analysis

**DATA1030 Final Project**  
**Student:** Justin Xiao  
**Institution:** Brown University  
**Date:** December 15, 2025  
**GitHub Repository:** [Earthquake-Tsunami](https://github.com/JustinXre2020/Earthquake-Tsunami)

---

## How to Run the Analysis

### Prerequisites
- Python 3.8 or higher
- Git (for cloning the repository)

### Installation Steps

1. **Clone the repository**:
   ```bash
   git clone https://github.com/JustinXre2020/Earthquake-Tsunami.git
   cd Earthquake-Tsunami
   ```

2. **Set up Python Virtual Environment**:

   **For Windows (PowerShell):**
   ```powershell
   # Create virtual environment
   python -m venv data1030
   
   # Activate virtual environment
   .\data1030\Scripts\Activate.ps1
   
   # Upgrade pip
   python -m pip install --upgrade pip
   
   # Install required packages
   pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter
   ```

   **For macOS/Linux (Bash/Zsh):**
   ```bash
   # Create virtual environment
   python3 -m venv data1030
   
   # Activate virtual environment
   source data1030/bin/activate
   
   # Upgrade pip
   python -m pip install --upgrade pip
   
   # Install required packages
   pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter
   ```

3. **Launch Jupyter Notebook** (with virtual environment activated):
   ```bash
   jupyter notebook src/source_code.ipynb
   ```
   Or use JupyterLab:
   ```bash
   jupyter lab src/source_code.ipynb
   ```

4. **Run all cells** in sequence using `Shift + Enter` or select `Cell > Run All` from the menu.

5. **Deactivate virtual environment** (when done):
   ```bash
   deactivate
   ```

### Data Requirements
Ensure the following CSV files are in the `data/dataset/` directory:
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
