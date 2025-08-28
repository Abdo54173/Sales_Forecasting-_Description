Walmart Weekly Sales Prediction
This project aims to predict the weekly sales for various departments in different Walmart stores using historical sales data and other relevant features like temperature, fuel price, and markdown events. The analysis and modeling are performed using Python with popular data science libraries.

Dataset
The project uses three separate datasets, which are merged together for a comprehensive analysis:

train.csv: Contains historical weekly sales data for each store and department, along with the Date and whether the week was a holiday.

features.csv: Includes additional features such as Temperature, Fuel_Price, CPI, Unemployment, and MarkDown information.

stores.csv: Provides details about each store, including its Size and Type.

Prerequisites
To run this project, you need the following Python libraries installed:

pip install numpy pandas matplotlib seaborn scikit-learn xgboost

Data Preprocessing and Feature Engineering
The following steps were taken to prepare the data for modeling:

Data Merging: The three datasets (train.csv, features.csv, and stores.csv) were merged into a single DataFrame based on the Store and Date columns.

Missing Value Handling: The MarkDown columns (MarkDown1 to MarkDown5) contained missing values, which were filled with 0 as these values represent weeks where no markdown events occurred.

Date Feature Extraction: The Date column was used to create new, useful features: Year, Month, Week, and DayOfWeek.

Lagged Features: To capture the time-series nature of the sales data, lagged features were created for Weekly_Sales. Weekly_Sales_lag1 represents the sales from the previous week, and Weekly_Sales_lag2 represents the sales from two weeks prior.

Categorical Encoding: The Type column, which is a categorical variable (A, B, C), was one-hot encoded to be used in the models. The IsHoliday column was also converted to an integer.

Data Splitting: The final dataset was sorted by Store, Dept, and Date, then split into a training set (data from years before 2012) and a testing set (data from 2012).

Modeling
Two regression models were trained and evaluated:

1. Linear Regression
A simple linear regression model was used as a baseline to predict weekly sales.

2. XGBoost Regressor
A more powerful and commonly used gradient boosting algorithm, XGBoost, was used to capture complex, non-linear relationships in the data. The model was configured with specific hyperparameters for better performance.

Evaluation Metrics
The performance of each model was evaluated using three standard regression metrics:

Root Mean Squared Error (RMSE): Measures the square root of the average of the squared differences between predicted and actual values. Lower values are better.

Mean Absolute Error (MAE): Measures the average of the absolute differences between predicted and actual values. Lower values are better.

R2 Score: Represents the proportion of the variance in the dependent variable that is predictable from the independent variables. A higher R2 score indicates a better fit.

Results
The models were evaluated on the test set (data from 2012).

Linear Regression Results
RMSE: 4410.47

MAE: 2217.20

R2 Score: 0.96

XGBoost Regressor Results
RMSE: 3644.54

MAE: 1667.12

R2 Score: 0.97

As shown by the evaluation metrics, the XGBoost model significantly outperformed the Linear Regression model, providing a much more accurate prediction of weekly sales.

Visualization
A plot comparing the actual and predicted weekly sales for a specific store and department (Store 1, Dept 1) is generated to visually assess the model's performance on a smaller, more interpretable scale.

The plot clearly shows how closely the XGBoost model's predictions align with the actual weekly sales data.
R² Score: 0.96025
