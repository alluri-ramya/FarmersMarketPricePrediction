# Farmers Market Price Analysis

**Hybrid AI system for forecasting agricultural commodity prices to optimize supply chain profits.**

## Overview
This project implements an end-to-end platform that predicts farmers' market prices using Agmarknet data, weather signals, and macroeconomic indices. It combines ARIMA/SARIMAX, Prophet with ML ensembles (XGBoost, LightGBM, Random Forest) to deliver robust forecasts with 7-9% MAPE accuracy across commodities like tomato, onion, and potato.[1]

## Key Features
- **Data Pipeline**: Ingests daily market prices, rainfall, NDVI, CPI, and holiday signals
- **Hybrid Models**: Classical time-series + tree-based ensembles with prediction intervals
- **Anomaly Detection**: Flags price shocks and supply disruptions
- **Dashboard**: Visualizes forecasts, actuals, and error heatmaps
- **Deployment**: FastAPI prediction service with MLflow model registry

## Results
| Commodity | Period | MAPE |
|-----------|--------|------|
| Tomato    | 2023-2024 | 8.5%[1] |
| Onion     | 2023-2024 | 7.2%[1] |
| Potato    | 2022-2024 | 9.1%[1] |

**Related Publication**: "Agriculture Supply Chain Management Profit Analysis Using A Hybrid Model" by Dr. JMSV Ravi Kumar[1]

## Setup & Usage
```bash
pip install -r requirements.txt
python src/ingest_data.py
python src/train_models.py
uvicorn src/api:app --reload
```

Visit `/predict` endpoint for real-time price forecasts.
