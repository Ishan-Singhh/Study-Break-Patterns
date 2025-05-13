# 📚 Study Break Patterns Analysis

This project analyzes the relationship between **study habits**, **break patterns**, and **self-reported productivity** using data collected via a **Google Form survey**.

---

## 📌 Objective

To understand how different study-related behaviors (such as break frequency, duration, distractions, phone usage, and break activities) influence students’ perceived productivity, and to identify key factors that may enhance or hinder study efficiency.

---

## 📊 Data Collection

The data was collected through a **Google Forms survey** filled out by students. The form included questions about:
- Daily study duration
- Number and duration of study breaks
- Distraction levels
- Phone usage habits
- Break activities (e.g., music, social media, walking)
- Whether structured methods like the Pomodoro technique are used
- Self-assessed productivity on a scale of 1 to 10

---

## 🧼 Data Preprocessing

The raw categorical responses were mapped to numerical values to facilitate analysis:

- **Study Hours**:
  - 'Less than 1 hour' → 0.5
  - '1-3 hours' → 2
  - '3-5 hours' → 4
  - '5+ hours' → 6

- **Break Frequency**:
  - '0-1' → 0.5
  - '2-3' → 2.5
  - '4-5' → 4.5
  - 'More than 5' → 6

- **Break Duration** (in minutes):
  - 'Less than 5 minutes' → 3
  - '5-10 minutes' → 7.5
  - '10-20 minutes' → 15
  - 'More than 20 minutes' → 25

- **Distraction and Phone Usage**:
  - Converted to scales (e.g., 'Yes, very often' → 3, 'No' → 0)

- **Break Activities**:
  - One-hot encoded (binary flags for each activity)

- **Structured Study Techniques**:
  - Yes → 2, Not Sure → 1, No → 0

The cleaned dataset was saved as `cleaned_data.csv`.

---

## 📈 Exploratory Data Analysis (EDA)

Visualizations included:
- Distribution plots for all numeric features
- Bar chart for most common break activities
- Correlation heatmap and covariance matrix

---

## 🧠 Model Building

A **Linear Regression** model was trained to predict the **productivity score** using the processed features.

### Features used:
- Study habits
- Break frequency/duration
- Distractions
- Phone proximity
- Break activity types
- Use of structured methods

### Evaluation Metrics:
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

Train-test split was 80/20. Polynomial regression (degree = 1) was used to verify linearity.

---

## 📉 Results

- Feature importances were evaluated using regression coefficients.
- Scatter plot of actual vs predicted productivity helped visualize model performance.
- Strong correlations were found with factors like:
  - Use of structured methods (Pomodoro)
  - Walk/stretch during breaks
  - Phone kept away
  - Fewer distractions

---

## 📁 Files

| File | Description |
|------|-------------|
| `Study Break Patterns.csv` | Raw Google Form responses |
| `cleaned_data.csv` | Preprocessed version of dataset |
| `graph.png` | Correlation heatmap |
| `study_break_analysis.ipynb` / `.py` | Python code for analysis and modeling |

---

## 🛠 Libraries Used

- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `sklearn` (LinearRegression, train_test_split, PolynomialFeatures, metrics)

---

## ✅ Key Insights

- **Walking/stretching**, **listening to music**, and **structured breaks** correlated with higher productivity.
- **Excessive phone usage** and **social media** during breaks were negatively associated.
- Balanced, consistent break habits showed better outcomes than random or excessive breaks.

---

## 🧠 Future Work

- Test non-linear models (e.g., Random Forest, XGBoost)
- Explore time-of-day or environment effects
- Use clustering to identify study behavior archetypes

---

