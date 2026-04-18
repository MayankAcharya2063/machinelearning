Nepal Telecom (NTC) Stock Price Prediction & Forecasting
This repository explores stock price movements for Nepal Telecom (NTC) using historical data from 2012 to 2025. The project demonstrates the application of regression and ensemble machine learning models to financial time-series data.

Project Highlights
Dual-Modeling Approach: Compares a "Same-Day Prediction" (estimation) against a "Next-Day Forecast" (prediction).
Technical Indicator Engineering: Implementation of RSI, MACD, Bollinger Bands, and Moving Averages.
Robust Pipeline: Includes Data Cleaning, Winsorization for outliers, and Time-Series Cross-Validation.

The Two Models1. 
1. Next-Day Forecasting (ntc_next_day_forecast.ipynb)
The Goal: Predict tomorrow's closing price based on today's indicators.
Features used: Today's Open, Volume, RSI, MACD, SMA, EMA, and ATR.
Target: Tomorrow's Close (T+1).
Use Case: This is the primary model for a realistic trading strategy. It answers: "Based on what I know now, what will the price be tomorrow?"
2. Same-Day Prediction (ntc_same_day_prediction.ipynb)
The Goal: Estimate the current day's closing price.
Features used: Today's Open, High, and Low.
Target: Today's Close (T).
Use Case: Useful for high-frequency estimation or detecting price anomalies within a single trading session. This model achieves very high accuracy (R^2 \approx 0.99) because the High/Low range strongly constrains the closing price.

Technical Implementation
  Data Preprocessing
    Feature Engineering: Calculated technical indicators to capture market momentum and volatility.
    Outlier Handling: Applied Winsorization to mitigate the impact of extreme spikes in Volume and Daily Returns.
    Scaling: Used MinMaxScaler fitted strictly on training data to prevent data leakage.

  Machine Learning Models
    Linear Regression: Used as a baseline to measure linear relationships.
    Random Forest Regressor: An ensemble model used to capture non-linear patterns and complex interactions between technical indicators.

  Validation Strategy
    Chronological Split: 80% Training / 20% Testing.
    Time-Series Cross-Validation: Utilized TimeSeriesSplit (5 folds) to ensure model stability over different market regimes (bull vs. bear markets).

Performance & Results
Sample Predictions (NPR)
A comparison of the actual market prices versus the model's predictions.

Visualizations
The notebooks include the following exploratory and result-based charts:
Price History: 10+ years of NTC price action.
Feature Importance: Visualizing which indicators (like RSI or Volume) influenced the Random Forest most.
Error Analysis: Actual vs. Predicted line charts for the test period.

Repository Structure
ntc_next_day_forecast.ipynb: Main forecasting pipeline.
ntc_same_day_prediction.ipynb: Intraday estimation model.
NTC.csv: The raw dataset (2012–2025).
images/: Folder containing generated plots and metrics.

How to RunClone the repository: git clone https://github.com/yourusername/NTC-Stock-Prediction.git
Install dependencies: pip install pandas numpy scikit-learn matplotlib seaborn
Run the Jupyter Notebooks to view results.

Disclaimer: This project is for educational and portfolio purposes only. Stock market investments carry inherent risks.
