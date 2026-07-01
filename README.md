# Exploratory Data Analysis (EDA) on Cardiotocography Data

This repository contains a comprehensive Exploratory Data Analysis (EDA) pipeline implemented in Python. The analysis focuses on a Cardiotocography dataset (`Cardiotocographic.csv`) to understand fetal heart rate (FHR) metrics, uterine contractions, and overall fetal well-being.

---

## Project Workflow

### 1. Data Cleaning & Preprocessing
*   **Missing Value Handling:** Automatically detects missing rows and drops columns with over 50% missing data. Remaining missing items are imputed using column means.
*   **Data Type Correction:** Identifies mixed data types and forces conversion of object columns into numerical `float64` values.
*   **Outlier Treatment:** Implements a Z-score filtering mechanism. Data points exceeding a threshold of $|Z| > 3$ are identified and safely replaced with the respective column's median value.

### 2. Descriptive Statistical Summary
*   Generates distribution metrics utilizing `df.describe()` to measure central tendency (mean, median) and dispersion (standard deviation, IQR) for critical parameters like baseline fetal heart rate (LB), accelerations (AC), and fetal movements (FM).

### 3. Data Visualization
Explores patterns and structural anomalies across variables using:
*   **Histograms & Boxplots** for overall feature spreads and distribution shapes.
*   **Bar & Pie Charts** to visualize demographic frequencies of FHR patterns and movements.
*   **Scatter Plots** tracking FHR Baseline against individual clinical features.
*   **Correlation Heatmaps & Pairplots** (via `seaborn` and `matplotlib`) to observe feature interactions.
*   **Violin Plots** featuring custom color palettes to look closely at density distributions.

### 4. Pattern Recognition & Insights
*   Computes complete correlation matrices to target key diagnostic interactions.
*   Includes built-in validation checks for temporal/datetime data columns to monitor baseline shifts over time.

---

## Key Clinical Insights
*   **Dataset Health:** The vast majority of records indicate healthy, standard fetal movement configurations (~70.3%) and a reactive fetal state.
*   **Contraction Impacts:** A weak positive correlation exists between the FHR baseline and uterine contraction frequency ($r = 0.17$), signaling that uterine contractions must be accounted for contextually during fetal evaluations.

---

## Requirements & Environment

Ensure you have Python 3.x installed along with the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scipy
