# Adv-stock-pattern-prediction
# Stock Price Prediction using LSTM

This project aims to predict future stock prices using a Long Short-Term Memory (LSTM) neural network model. The model is trained on historical stock data, specifically daily closing prices, to forecast future closing prices.

## Dataset

The dataset used in this project consists of historical daily closing prices of Apple (AAPL) stock, fetched using the `yfinance` library. The data spans from January 1, 2020, to January 1, 2024.

## Preprocessing

The raw stock data is preprocessed before being fed into the LSTM model. This includes:

- **Scaling:** The closing prices are scaled using `MinMaxScaler` to normalize values between 0 and 1, ensuring that all features contribute equally to model training.
- **Sequence Creation:** Input sequences of 60 days are created, where each sequence represents the closing prices for the past 60 days, and the corresponding target is the closing price on the 61st day.

## Model Architecture

The LSTM model consists of three LSTM layers followed by a Dense layer. The LSTM layers capture temporal dependencies in the stock price data, while the Dense layer maps the LSTM output to a single predicted closing price.

## Training

The model is trained using the Adam optimizer and mean squared error loss function. Early stopping is implemented to prevent overfitting, and model checkpoints are saved to preserve the best performing model.

## Evaluation

The model's performance is evaluated on a test set using metrics such as Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

## Prediction

The trained model is used to predict closing prices for the next 4 days. The predictions are visualized alongside historical data using `matplotlib` and `mplfinance`.

## Dependencies

The following libraries are required to run this project:

- `tensorflow`
- `keras`
- `yfinance`
- `numpy`
- `pandas`
- `matplotlib`
- `mplfinance`
