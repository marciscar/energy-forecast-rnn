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
├─ data/ # raw CSVs    
├─ README.md    

---

## Results

