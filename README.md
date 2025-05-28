
# Stock Price Prediction using Time Series Models

This project predicts stock prices using three different machine learning models: **XGBoost**, **LSTM (Neural Network)**, and **Facebook Prophet**. It includes data preprocessing, feature engineering, training, and deployment using a **Flask REST API**.

---

## Models Used

1. **XGBoost Regressor**  
   - Uses engineered features like open, high, low, volume, and date components.
   - Tuned using GridSearchCV.
   - Good for tabular regression.

2. **LSTM (Long Short-Term Memory)**  
   - Deep learning model using 60-day rolling windows.
   - Scaled with MinMaxScaler.
   - Suitable for capturing time dependencies in sequences.

3. **Prophet (by Meta/Facebook)**  
   - Designed for time series with trend and seasonality.
   - Automatically handles missing data and holidays.

---

## Project Structure

```
.
├── RELIANCE.NS_stock_data.csv      # Dataset (NSE stock data)
├── Stock_Prediction(time_series).ipynb  # Main Jupyter notebook
├── xgb_model.pkl                   # Trained XGBoost model
├── lstm_model.h5                   # Trained LSTM model
├── prophet_model.pkl              # (Optional) Trained Prophet model
├── app.py                          # Flask API for serving predictions
├── requirements.txt                # Python dependencies
└── README.md                       # This file
```

---

## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/stock-prediction-api.git
cd stock-prediction-api
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Flask Server

```bash
python app.py
```

Server will start at: [http://127.0.0.1:5000](http://127.0.0.1:5000)

---

## API Usage

### POST `/predict`

Send a JSON payload with the model you want to use and its input features.

#### XGBoost Example:

```json
{
  "model_id": "xgb",
  "features": [1120, 1135, 1110, 200000, 2024, 5, 28, 2]
}
```

#### LSTM Example:

```json
{
  "model_id": "lstm",
  "features": [0.45, 0.46, ..., 0.52]  // 60 normalized close prices
}
```

#### Response:

```json
{
  "prediction": [1132.23]
}
```



## Requirements

- Python 3.8+
- Flask
- scikit-learn
- xgboost
- tensorflow
- prophet
- numpy, pandas, seaborn, matplotlib

---

##  Authors

**Fatma Al-Junaibi**  
**Shaima Al-Wahaibi**  


---

 
