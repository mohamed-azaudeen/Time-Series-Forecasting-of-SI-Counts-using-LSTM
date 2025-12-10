# Time-Series-Forecasting-of-SI-Counts-using-LSTM

This project focuses on **time series forecasting** of **SI (Shipping Instruction) counts** using advanced deep learning techniques.  
The workflow includes **EDA, hypothesis testing, model comparison (ARIMA, SARIMAX, Prophet, LSTM, GRU)**, and final selection of a fine-tuned **LSTM model** with advanced architectures.

---

## 🚀 Project Highlights
- **Exploratory Data Analysis (EDA)**  
  - Time-based resampling (hourly SI counts).  
  - Feature engineering: day of week, weekend indicator, hourly trends.  
  - Visualization of SI patterns and anomalies.  

- **Hypothesis Testing**  
  - Checked seasonality, stationarity, and autocorrelation.  
  - Validated assumptions for statistical models (ARIMA/SARIMAX).  

- **Model Comparison**  
  - **ARIMA / SARIMAX** → Captured linear trends but struggled with long-term dependencies.  
  - **Prophet** → Good for seasonality but less accurate for fine-grained hourly data.  
  - **GRU** → Competitive but slightly underperformed compared to LSTM.  
  - **LSTM** → Best performance with ability to capture long-term dependencies.  

- **Advanced LSTM Architectures**  
  - **Stacked LSTM** → Multiple layers for deeper feature extraction.  
  - **Bidirectional LSTM** → Captures dependencies in both forward and backward directions.  
  - **Conv2D LSTM** → Combines convolutional feature extraction with temporal modeling.  
  - After experimentation, **standard LSTM** was finalized as the best-performing model.  

---

## 🧠 Model Details
- **Input Features**:  
  - SI count (hourly)  
  - Day of week  
  - Weekend indicator  

- **Preprocessing**:  
  - MinMax scaling  
  - Sequence length = 720 hours (30 days)  
  - Forecast horizon = 1440 hours (60 days)  

- **Final Model**:  
  - LSTM with 128 units  
  - Dropout = 0.2  
  - Dense output layer predicting 1440 future hours  
  - Optimizer: Adam  
  - Loss: Mean Squared Error (MSE)  
  - Early stopping applied  

---

## 📊 Evaluation Metrics
- **MAE (Mean Absolute Error)**  
- **RMSE (Root Mean Squared Error)**  
- **MAPE (Mean Absolute Percentage Error)**  
- **R² (Coefficient of Determination)**  

# Example output:
MAE : 12.45 
RMSE : 18.32 
MAPE : 8.76% 
R² : 0.89

---

## 📈 Visualization
- **Training Progress**: Loss vs Epochs (Train & Validation).  
- **Forecast Results**: Actual vs Predicted SI counts plotted over time.  
- **Bucket Classification**: Predictions categorized into ranges (Exact Match, ±3, ±5, ±10, >±10).  

---
