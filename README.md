# Energy Demand Forecasting with LSTM (PyTorch)

Forecasting short-term electricity demand using **Recurrent Neural Networks (RNNs)**, implemented with **PyTorch**.  
Accurate load forecasting is critical for energy providers to optimize generation, pricing, and integration of renewable sources.  

---

## Dataset
- **Source**: [PJM Hourly Energy Consumption (Kaggle)](https://www.kaggle.com/robikscube/hourly-energy-consumption)  
- **Features used**:  
  - Datetime (hourly frequency)  
  - Electricity demand (MW)  


---

## Project Goals
- Forecast **next-hour demand** using the previous 24 hours of data.  
- Compare against **naïve and seasonal baselines**.  
- Extend to **multi-step (24-hour ahead)** forecasting.  

---

## Repository Structure

energy-forecast-rnn/    
├─ energy-forecast-rnn.ipynb # Notebook     
├─ figures/     
│    └─ forecast_plot.pdf    # Plot showing the performance of the model    
├─ data/ # raw CSVs    
├─ models/  # Saved checkpoints (ignored by Git)    
├─ README.md    

---

## Results

**Performance summary**

| Forecast Horizon | MAE (MW) | RMSE (MW) | R² |
|------------------:|----------:|-----------:|----:|
| 24 hours          | 1,097.8  | 1,526.1    | 0.946 |
| 1 week            | 3,903.1  | 4,937.7    | 0.460 |

The model shows strong short-term performance, capturing the daily pattern of electricity demand accurately (R² ≈ 0.95 for 24-hour forecasts).  
As the forecast extends further into the week, errors accumulate (R² ≈ 0.46), which is expected for an autoregressive LSTM model — each prediction is generated using previous model outputs, so small deviations compound over time.  
In practical applications, forecasts can be refined dynamically as new hourly data become available, improving accuracy for the later parts of the prediction horizon.