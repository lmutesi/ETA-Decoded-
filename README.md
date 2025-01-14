# Predicting Flight Arrival Delays

## Ensuring You Stay on Schedule for What Matters Most

### Project Overview
Flight delays disrupt schedules, causing inconvenience for passengers, airlines, and airports, alongside significant economic costs. Our project tackles two key questions:

1. **Will a flight be delayed?**

2. **If delayed, how severe will the delay be?**

By predicting delay likelihood and duration using operational and flight data, we aim to optimize airline operations, enhance passenger satisfaction, and streamline airport processes.

### Dataset
Source: Kaggle - Flight Delay Dataset (2018–2022)

Focus Year: 2021

- **Initial Shape**: 6,311,871 rows, 61 columns

- **Processed Shape**: 6,185,870 rows, 26 features

#### Target Variables:

 - **Binary Prediction**: ArrDel15 (delayed or not)

- **Continuous Prediction**: ArrDelayMinutes (delay duration in minutes)

- **Categorical Prediction**: ArrivalDelayGroups (severity of delays)

Key cleaning steps included removing invalid entries, resolving data imbalance (~83% non-delayed flights), addressing multicollinearity, and outlier capping.

### Methods and Techniques
#### Pre-Processing & Feature Engineering
- Engineered features like **Weekend Indicators**, **Seasonal Labels**, and **Delay Trends by Aircraft**.
- Addressed data leakage by excluding correlated target-related features.
- Scaled numerical variables and applied one-hot encoding for categorical data.

### Models Built
##### Binary Classification (Will a flight be delayed?)
- **Algorithms**: Logistic Regression, Decision Trees, Random Forest
- **Metrics**: Precision, Recall, F1 Score, AUC
- **Optimization**: Hyperparameter tuning, threshold adjustments, class balancing

### Regression (How long will the delay last?)
- **Algorithms**: Ridge, Lasso, Polynomial Ridge Regression
- **Metrics**: RMSE, MAE, R²
- **Optimization**: Feature selection, hyperparameter tuning, and interaction features like `Distance_AvgDelays`.

#### Key Results
#### Model 1: Binary Classification
- **Best Model**: Random Forest
- **Performance**:
  - Accuracy: 69.6%
  - Recall: 79.1%
  - F1 Score: 47.3%

#### Model 2: Regression
- **Best Model**: Polynomial Ridge Regression
- **Performance**:
  - RMSE: 16.87 minutes
  - MAE: 11.10 minutes
  - R²: 7%

### Real-World Implications
- **Airlines**: Better scheduling and resource allocation.
- **Passengers**: Improved predictability for alternate travel plans.
- **Airports**: Efficient runway and gate operations.

Challenges remain due to missing real-time data (e.g., weather, maintenance logs). Adaptive models with live data integration would have helped further improvements in model perfomance


### Key Files
- **Data Preprocessing**: `Data_Cleaning_EDA_Initial_Feature_Selection.ipynb`
- **Binary Classification**:
  - `Logistic_Regression_Model_and_Evaluation.ipynb`
  - `DMA_Final_Project_Arrival_delay_prediction_DT.ipynb`
  - `RandomForestEvaluation.ipynb`
- **Regression Modeling**:
  - `DMA_FINAL_PROJECT_Regression_Model.ipynb`

### Documentation
## Documentation
- [Final Project Report](https://github.com/lmutesi/ETA-Decoded-/blob/main/DMA%20Final%20Project%20Report_ETA%20Decoded.pdf)
- [Presentation Deck](https://github.com/lmutesi/ETA-Decoded-/blob/main/Frequent%20Flyers_ETA%20Decoded%20.pdf)


### Lessons Learned
- Balancing recall and precision is critical in high-stakes predictions.
- Large datasets require efficient subsampling and feature selection to manage computation.
- Addressing data leakage is key to realistic predictions.
