📈 Stock Price Prediction: AAPL & Climate Trends
A comparative study using LSTM (Deep Learning) and Facebook Prophet (Time-Series Analysis).

📖 Overview
This project predicts stock price movements and climate trends using historical data. The goal was to compare the performance of Long Short-Term Memory (LSTM) networks against Facebook Prophet to understand which model handles volatility better versus seasonal trends.

Key Features
Multivariate LSTM: Uses Open, High, Low, Close, and Volume to predict the next day's price.

Prophet Forecasting: Analyzes yearly and weekly seasonality in market trends.

Data Pipeline: Includes automated scaling, chronological train-test splitting, and gap interpolation for weekends.

🛠️ Tech Stack
Python 3.x

TensorFlow/Keras: For building and training the LSTM.

Facebook Prophet: For additive/multiplicative forecasting.

Scikit-Learn: For MinMaxScaler and StandardScaler preprocessing.

Pandas/Numpy: Data manipulation and windowing logic.

Matplotlib: Visualization of loss curves and predictions.

🚀 Getting Started
1. Installation
Clone the repository and install the dependencies:

Bash
git clone: https://github.com/Midhun-P-Jose/stock_price.git
cd stock-prediction-lstm
pip install -r requirements.txt

2. Data Setup
Since datasets are ignored in this repository (via .gitignore), follow these steps:

Download the AAPL.csv from Yahoo Finance.

Place the file in the root directory (or /data folder).

Ensure the CSV has the following columns: Date, Open, High, Low, Close, Adj Close, Volume.

3. Run the Model
Open the Jupyter Notebook or run the script:

Bash
jupyter notebook lstm_prediction.ipynb
📊 Model Performance
LSTM Results
Window Size: 30 Days

Architecture: Stacked LSTM (64, 32 units) with Dropout (0.2).

Outcome: Captured short-term volatility well but required careful scaling to prevent data leakage.

Prophet Results
Components: Yearly, Weekly seasonality.

Outcome: Excellent at identifying long-term growth trends and handling market holidays automatically.

🧠 Lessons Learned
Data Leakage: I learned that scaling the entire dataset before splitting leads to "cheating." Scaling must be fitted only on training data.

Temporal Continuity: Discovered the importance of interpolation to handle weekends, ensuring the LSTM has a consistent 24-hour heartbeat.

Stationarity: Interpreted how market volatility affects the "Vanishing Gradient" in long-sequence LSTMs.

The actual vs predicted:
For Prophet:
<img width="552" height="413" alt="image" src="https://github.com/user-attachments/assets/a1c894d8-8521-407a-b39b-3ae37650c865" />
For LSTM:
<img width="552" height="413" alt="image" src="https://github.com/user-attachments/assets/1d9c5c70-18b3-425b-b14a-0e6df2660142" />
