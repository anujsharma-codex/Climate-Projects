# Climate Projects

This is my applied project portfolio in **climate physical risk intelligence** — a field at the intersection of atmospheric physics, data science, and risk assessment.

Every project here is built to solve a real climate data problem. Each one represents the applied output of a learning stage — not toy examples, but domain-specific systems that get progressively more sophisticated as the technical stack grows.

The learning record behind these projects lives in → **[Climate-Data-Science-Learning-Record](https://github.com/anujsharma-codex/Climate-Data-Science-Learning-Record)**

---

## Projects

### `01_SOLAR_POTENTIAL_CALCULATOR/` — (v1.0 & v2.0) ✅
**Stack:** Python, OOP, NumPy

This project evaluates solar panel installation viability for residential and commercial properties across India. It has evolved through two distinct phases:
- **v1.0 (Pure Python):** Built without external libraries to demonstrate clean algorithmic thinking, factory patterns, and robust OOP architecture.
- **v2.0 (NumPy Integrated):** A high-performance refactor that introduces **vectorization**, structured arrays, and 25-year lifecycle degradation modeling using NumPy.

→ [Project Evolution README](01_SOLAR_POTENTIAL_CALCULATOR/README.md)

---

### `02_EXTREME_WEATHER_ANALYZER/` — *(coming soon)*
**Stack:** Pandas, NumPy, Matplotlib, Xarray

Analysis of 20+ years of climate data to identify and visualise trends in extreme weather events across India. Uses ERA5 reanalysis data in NetCDF format. Will include anomaly detection, rolling climate normals, and visualisation of how frequently "once-in-a-decade" events now occur.

---

### `03_HYDROMET_STATION_DATABASE/` — *(planned)*
**Stack:** PostgreSQL, PostGIS, Window Functions

A relational database for a network of hydrometeorological stations. Normalised schema covering stations, sensors, and readings. Spatial queries to find stations within a radius reporting threshold rainfall. Window functions for rolling averages per station.

---

### `04_CLIMATE_SIGNAL_DETECTOR/` — *(planned)*
**Stack:** SciPy, StatsModels, NumPy

Statistical analysis to determine whether observed temperature and precipitation trends are statistically significant. Mann-Kendall trend tests, Gumbel distribution fitting for extreme event return periods, bootstrapped uncertainty estimates, and Bayesian changepoint detection.

---

### `05_DUNKELFLAUTE_PREDICTOR/` — *(planned)*
**Stack:** PyTorch or TensorFlow, Scikit-learn, ERA5 data

A forecasting model to predict Dunkelflaute — periods of simultaneous low wind and low solar generation that stress renewable energy grids. 72-hour ahead forecasts from atmospheric variables, compared against persistence and climatology baselines.

---

### `06_CLIMATE_RISK_PLATFORM/` — *(planned)*
**Stack:** FastAPI, PostgreSQL/PostGIS, MLflow, Docker, Streamlit/React

An end-to-end climate risk intelligence platform. Physics-Informed Neural Networks constrained by energy conservation equations. Automated retraining pipeline. Interactive map for probabilistic regional forecasts with uncertainty bounds. Auto-generated PDF risk reports for policymakers.

---

## Roadmap

| Project | Stack | Domain Problem | Status |
|---|---|---|---|
| Solar Potential Calculator | Python, OOP, NumPy | Rooftop solar viability and ROI | ✅ v1 & v2 complete |
| Extreme Weather Analyzer | Pandas, NumPy, Xarray | Trend detection in climate extremes | 🔄 Up next |
| Hydromet Station Database | PostgreSQL, PostGIS | Fragmented station data unification | ⏳ Planned |
| Climate Signal Detector | SciPy, StatsModels | Statistical significance of climate trends | ⏳ Planned |
| Dunkelflaute Predictor | PyTorch, ERA5 | Renewable energy generation forecasting | ⏳ Planned |
| Climate Risk Platform | FastAPI, Docker, React | End-to-end risk intelligence system | ⏳ Planned |

---

## Domain

These projects sit at the intersection of three fields:

```
Atmospheric Physics  ×  Data Science  ×  Risk Assessment
        ↓                    ↓                  ↓
  Climate dynamics      ML + Statistics     Energy, Insurance,
  Energy balance        Uncertainty quant.  Policy, Finance
        
                  CLIMATE PHYSICAL RISK INTELLIGENCE
```

The target roles this portfolio builds toward: Climate Data Scientist, Renewable Energy Forecaster, Catastrophe Modeler, Climate Risk Analyst.

---

## About

I'm building domain-specific data science skills with a clear target: climate physical risk intelligence. Every project is chosen to solve a real problem in the field and to demonstrate a progressively more sophisticated technical stack — from pure Python to physics-aware ML systems in production.

Learning record and foundations → **[Climate-Data-Science-Learning-Record](https://github.com/anujsharma-codex/Climate-Data-Science-Learning-Record)**
