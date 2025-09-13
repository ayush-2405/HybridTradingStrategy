# Algorithmic Trading Strategy with Machine Learning and Rule-Based Signals

This project implements a simple algorithmic trading strategy that combines rule-based signals with a Machine Learning model (Random Forest) to generate trading signals for a given stock ticker. The strategy is backtested to evaluate its performance.

## Project Structure

The project is organized into several functions, each responsible for a specific part of the trading strategy:

1.  **Utilities / Indicators**: Functions to calculate technical indicators like SMA, EMA, RSI, MACD, and Bollinger Bands.
2.  **Feature Engineering**: Adds calculated technical indicators and other relevant features (returns, volatility, lag features) to the price data.
3.  **Label Generation**: Creates a binary label for the Machine Learning model based on future price movements.
4.  **Rule Signals**: Generates trading signals based on predefined technical analysis rules (e.g., SMA crossover, RSI conditions).
5.  **ML Model Training**: Trains a Random Forest classifier to predict the target label using the engineered features.
6.  **Combine Signals**: Combines the rule-based signals and the ML model's predictions to generate a final trading signal.
7.  **Backtester (Daily Loop)**: A simple backtesting engine that simulates trades based on the combined signals, tracking equity, cash, and position.
8.  **Performance Metrics**: Calculates key backtesting performance metrics like Cumulative Return, Annualized Return, Sharpe Ratio, Max Drawdown, etc.
9.  **Main Runnable Example**: A main function that orchestrates the entire process, from data download to backtesting and plotting results.

## How to Use

1.  **Clone the Repository**: Clone this repository to your local machine or open it in Google Colab.
2.  **Install Dependencies**: Ensure you have the necessary libraries installed. If using Google Colab, most are pre-installed. Otherwise, you might need to install `yfinance`, `pandas`, `numpy`, `scikit-learn`, and `matplotlib`.
3.  **Run the Main Function**: Execute the `main()` function. You can modify the `ticker`, `start`, and `end` dates within the `main()` function to analyze different stocks and time periods.
4.  **Analyze Results**: The script will output ML metrics, backtesting performance metrics, and plot the equity curve and price with trade signals.


## Customization

*   **Ticker and Date Range**: Modify the `ticker`, `start`, and `end` variables in the `main()` function to analyze different stocks and time periods.
*   **Technical Indicators**: Add or modify technical indicators in the `add_indicators` function.
*   **Rule-Based Signals**: Adjust the logic in the `rule_signals` function to change the rule-based strategy.
*   **Machine Learning Model**: Experiment with different ML models and hyperparameters in the `train_ml_model` function.
*   **Feature Engineering**: Modify the `feature_cols` list in the `main()` function to include or exclude features for the ML model.
*   **Signal Combination**: Adjust the `ml_threshold`, `rule_weight`, and `ml_weight` in the `combined_signal` function to change how the signals are combined.
*   **Backtesting Parameters**: Modify `initial_cash`, `commission`, and `slippage` in the `BacktestEngine` initialization to simulate different trading conditions.

## Results

The output of the `main()` function will show the performance metrics of the backtested strategy and plots of the equity curve and trade signals on the price chart.

**Note**: This is a simplified example for educational purposes. Real-world algorithmic trading requires more sophisticated techniques, risk management, and rigorous testing.
