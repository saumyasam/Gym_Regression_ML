# Predicting Weight from Gym Exercise Dataset using Linear Regression

## Project Overview
This project aims to build a linear regression model to **predict gym members' weight (kg)** based on various health and activity features such as height, age, exercise level, and workout metrics. The dataset used comes from a Kaggle source: [Gym Members Exercise Dataset](https://www.kaggle.com/datasets/valakhorasani/gym-members-exercise-dataset).

---

## Dataset Description

The dataset includes **973 entries** and multiple health-related features:

- **Age, Gender**
- **Weight (kg)** — (target)
- **Height (m)**
- **Max/Avg/Resting BPM**
- **Workout Type, Session Duration**
- **Calories Burned**
- **Fat Percentage, Water Intake**
- **Workout Frequency (days/week)**
- **Experience Level** (1 = beginner, 3 = expert)
- **BMI** — derived metric

---

## Problem Statement

Can we accurately predict a gym member’s **weight** based on measurable attributes such as age, height, experience, and exercise-related features?

---

## Process Summary

1. **Data Preprocessing**
   - Handled missing values.
   - Applied one-hot encoding for categorical variables like `Gender` and `Workout_Type`.
   - Selected a set of features that logically correlate with weight.

2. **Model Selection**
   - Chose **Linear Regression** for its interpretability and simplicity.
   - Features used:  
     `['Height (m)', 'Age', 'Experience_Level', 'Session_Duration (hours)', 'Workout_Frequency (days/week)', 'Calories_Burned', 'Avg_BPM', 'Gender_Male']`

3. **Model Evaluation**
   - Used **Mean Squared Error (MSE)** as the primary metric.
   - **MSE = 304.23**

---

## Results & Visualization

![Actual vs Predicted Weight](actual_vs_predicted)

- The plot shows a wide spread around the ideal prediction line (in red).
- There's clear evidence of **underfitting** and non-linear behavior not well captured by a simple linear model.

---

## Reflection

- **Model Performance:**  
  With an MSE of **304.23**, the model's predictions are quite far from the actual values. The output plot confirms poor linear fit, likely due to:
  - **Non-linearity** in the data
  - **Unscaled features**
  - **Omitted interactions or derived metrics (like BMI or Fat%)**

- **Lesson Learned:**  
  Linear regression, while interpretable, has limited capacity to model complex relationships in health and fitness data. This experiment reinforces the importance of **exploratory analysis, model choice, and feature engineering** in machine learning pipelines.

---

## File Structure

```
├── healthcare_weight_prediction.ipynb  # Main notebook
├── gym_members.csv                     # Input data
├── 5c71b25c-9867-4d81-b290-15614a08321b.png  # Prediction plot
└── README.md                           # Project summary and reflection
```

---

## Credits

Dataset: [Kaggle - Gym Members Exercise Dataset](https://www.kaggle.com/datasets/valakhorasani/gym-members-exercise-dataset)  
Author: Saumya Padhi  
Course: MGT-665-NW | Solving Problems with Machine Learning
