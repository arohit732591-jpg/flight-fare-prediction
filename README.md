# ✈️ Flight Fare Prediction Using Machine Learning

## 1. Project Overview

Flight ticket prices can vary depending on several factors, including airline, journey date, source, destination, number of stops, and flight duration.

The objective of this project is to analyze flight fare data and develop machine learning regression models to predict ticket prices.

This project demonstrates an end-to-end machine learning workflow, from data cleaning and exploratory data analysis to feature engineering, model training, hyperparameter tuning, and evaluation.

## 2. Business Objective

To build a predictive model that helps travelers estimate flight ticket prices and plan their journeys.

The project also explores how different flight-related features are associated with ticket prices.

## 3. Dataset Description

**Dataset file:** `Flight_Fare.xlsx`

- Number of original records: 10,683
- Number of columns: 11
- Data source: Provided by my academic institution, with permission for public sharing.

### Features

| Feature | Description |
|---|---|
| Airline | Name of the airline |
| Date_of_Journey | Date of the journey |
| Source | Journey starting location |
| Destination | Journey destination |
| Route | Flight route |
| Dep_Time | Departure time |
| Arrival_Time | Arrival time |
| Duration | Total flight duration |
| Total_Stops | Number of stops |
| Additional_Info | Additional flight information |
| Price | Flight ticket price (target variable) |

## 4. Data Cleaning and Preprocessing

The following preprocessing steps were performed:

- Checked missing values and duplicate records.
- Removed rows containing missing values.
- Removed duplicate records.
- Converted journey dates into numerical date features.
- Converted flight duration into minutes.
- Extracted departure and arrival hours and minutes.
- Converted the number of stops into numerical values.
- Removed `Additional_Info` because most observations contained limited information (`No info`).
- Applied one-hot encoding to Airline, Source, and Destination.
- Removed Route to avoid creating a large number of additional categorical features.

After cleaning, the dataset contained 10,462 rows and 11 columns.

## 5. Exploratory Data Analysis (EDA)

Exploratory analysis was performed to understand the relationship between flight features and ticket prices.

The analysis included:

- Distribution of flight ticket prices.
- Price comparison across airlines.
- Price variation based on the number of stops.
- Average prices by source and destination.
- Correlation analysis of numerical features.
- Relationship between flight duration and ticket prices.
- Price variation across journey months.

## 6. Feature Engineering

The following numerical features were created:

- Journey_Day
- Journey_Month
- Duration_Minutes
- Dep_Hour
- Dep_Minute
- Arrival_Hour
- Arrival_Minute

Categorical variables were converted into numerical representations using one-hot encoding.

## 7. Model Development

The dataset was divided into training and testing sets using an 80:20 split.

The following regression models were evaluated:

1. Linear Regression
2. Random Forest Regressor
3. Gradient Boosting Regressor
4. XGBoost Regressor
5. Tuned Random Forest using GridSearchCV
6. Tuned XGBoost using GridSearchCV

## 8. Model Evaluation

The models were evaluated using three metrics:

- **MAE (Mean Absolute Error):** Measures the average absolute prediction error.
- **RMSE (Root Mean Squared Error):** Measures prediction error while giving greater weight to larger errors.
- **R² Score:** Measures the proportion of target-variable variance explained by the model.

### Model Comparison Results

| Model | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Linear Regression | 1998.639 | 2945.796 | 0.584 |
| Random Forest | 1172.376 | 1965.972 | 0.815 |
| Gradient Boosting | 1536.422 | 2267.571 | 0.753 |
| XGBoost | 1254.643 | 1897.463 | 0.827 |
| Tuned Random Forest | 1125.577 | 1847.875 | 0.836 |
| Tuned XGBoost | 1159.251 | 1810.417 | 0.843 |

## 9. Final Model and Key Findings

Tuned XGBoost was selected as the final model because it achieved the highest R² score and the lowest RMSE among the evaluated models.

Its recorded test-set performance was:

- MAE: ₹1,159.25
- RMSE: ₹1,810.42
- R² Score: 0.843

Tuned Random Forest achieved the lowest MAE of ₹1,125.58.

The results show that the tree-based ensemble models performed better than the baseline Linear Regression model on this test split.

## 10. Error Analysis

Residual analysis was performed using:

- Residual distribution plot.
- Residuals versus predicted values plot.
- Actual versus predicted price comparisons.

These visualizations help examine the distribution and patterns of prediction errors.

## 11. Technologies and Libraries

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost

## 12. Repository Structure

```text
flight-fare-prediction/
│
├── Flight.ipynb
├── Flight_Fare.xlsx
└── README.md
```

## 13. How to Run This Project

1. Clone or download this repository.
2. Open the project folder in VS Code or Jupyter Notebook.
3. Install the required Python libraries.
4. Ensure `Flight_Fare.xlsx` is in the same folder as the notebook.
5. Open `Flight.ipynb` and execute the notebook cells in order.

Install the main dependencies using:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost openpyxl jupyter
```

## 14. Limitations and Future Improvements

- The dataset is mainly from 2019, so the model may not reflect current flight pricing patterns.
- Booking time, demand, and seat availability are not included.
- Model performance on historical data does not guarantee accuracy for current or future flight prices.

Potential improvements include using more recent data, adding relevant booking and demand features, and exploring additional model optimization techniques.

## 15. Conclusion

This project demonstrates a complete machine learning regression workflow for flight fare prediction.

Six model configurations were compared, and tuned XGBoost achieved the strongest overall performance based on R² and RMSE, while tuned Random Forest achieved the lowest MAE.

The project provided practical experience in data preprocessing, exploratory data analysis, feature engineering, regression modeling, hyperparameter tuning, and model evaluation.

---

**Author:** A ROHIT

**Project Type:** Academic Machine Learning Project

**Domain:** Data Science | Machine Learning | Regression