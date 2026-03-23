<<<<<<< HEAD
# ☀️ Solar Potential Calculator (V2)
### *From Pure Python to the NumPy Data Engine*

![Solar Calculator V2](file:///C:/Users/anujs/.gemini/antigravity/brain/b4b2add4-25be-4de5-babb-ed6a26126c07/solar_calculator_banner_v2.png)

## 🚀 The V2 Transformation
Phase 2 of my learning roadmap transitions this professional solar tool from basic scalar calculations to a **high-performance NumPy engine**. While V1 demonstrated clean **OOP design**, V2 leverages **vectorization** to handle multi-dimensional data and life-cycle analytics.

---

## 🛠 What's New in V2?

| Feature | V1 (Basic Python) | V2 (NumPy Powered) | Why it Matters? |
| :--- | :--- | :--- | :--- |
| **Data Structure** | Python Dictionaries | **NumPy Structured Arrays** | Efficient memory and row-based record filtering. |
| **Time Analysis** | Annual Average (Scalar) | **12-Month Array (Vectorized)** | Monthly seasonal variation handled in one operation. |
| **Life Cycle** | Constant Performance | **25-Year Degradation Array** | Models real-world efficiency loss (0.5% yearly decay). |
| **Indexing** | Key-Value Lookups | **Boolean Search & Masking** | Professional data-science method for record retrieval. |

---

## 🏗 Architecture: The "NumPy Core"
The core classes from V1 remain, but their internal logic has been "supercharged":

1.  **`config.py`**: Now uses `np.array` with custom `dtypes` for Cities, States, and Subsidies.
2.  **`Solar/Location`**: Uses NumPy **Boolean Masking** (`np.where`) to find location data instantly.
3.  **`Solar/EnergyGeneration`**: Calculates energy for all 12 months in a single vectorized calculation—**zero loops**.
4.  **`Solar/Finance`**: Models a 25-year financial horizon considering panel wear-and-tear using `np.cumprod`.

---

## 📊 Technical Highlights

### **1. Vectorized Month Analytics**
Instead of calculating one day and multiplying by 30, V2 uses a "Days-Per-Month" array:
```python
# One line calculates specific energy for every month in the year
monthly_gen = daily_energy * np.array([31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31])
```

### **2. Lifecycle Performance Decay**
We model 25 years of investment by creating a degradation curve:
```python
# Each year is 0.5% less efficient than the last
degradation = 0.995 ** np.arange(25)
total_lifetime_energy = np.sum(annual_energy * degradation)
```

---

## 🛣 Learning Roadmap
- [x] **V1: Core Python & OOP** (The Foundation)
- [x] **V2: NumPy Integration** (The Engine - *Current*)
- [ ] **V3: Pandas DataFrames** (The Analysis Suite)
- [ ] **V4: Matplotlib & Seaborn** (The Visual Dashboard)
- [ ] **V5: NSRDB/NASA APIs** (The Real-World Data)

---

## 💻 How to Run
```bash
# Clone the repository
cd V2_SOLAR_POTENTIAL_CALCULATOR

# Install dependencies (NumPy is all you need!)
pip install numpy

# Run the analyzer
python main.py
```

---

## ✍️ Author
Built as part of a **Climate Physical Risk Intelligence** roadmap — demonstrating the transition from algorithmic logic to data-driven performance modeling.
=======
# Python Learning Journey

This repository is my **learning record** — every concept I studied, every exercise I solved, and every mini-project I built while working toward my goal of becoming a climate physical risk data scientist.

It is not a portfolio repo. It is the work behind the portfolio.

The finished, production-grade projects built from these skills live in → **[Climate Projects](https://github.com/anujsharma-codex/Climate-Projects)**

---

## Structure

### `01_Fundamentals/`
Practice exercises written while learning core Python from scratch. Organised by concept — strings, lists, dictionaries, functions, error handling, and OOP. These are the building blocks, solved one concept at a time.

```
01_Fundamentals/
├── strings/
├── lists/
├── dictionaries/
├── functions/
├── error_handling/
└── classes/
```

### `02_PROJECT_PYTHON_CORE+OOPS/`
First applied project built using pure Python and OOP — no external libraries. Demonstrates that the fundamentals from Stage 1 can be combined into a real, working system.

→ **Solar Potential Calculator** — CLI tool to evaluate solar panel installation viability for residential and commercial users across 9 Indian cities. Calculates system sizing, energy output, government subsidies, GST, payback period, and LCOE.

The full production version of this project lives in [Climate Projects](https://github.com/anujsharma-codex/Climate-Projects).

### `03_Libraries/` *(coming soon)*
Practice and mini-projects for each data science library — pandas, NumPy, Matplotlib, and xarray. Each subfolder covers one library with focused exercises and small experiments.

```
03_Libraries/          ← coming soon
├── pandas/
├── numpy/
├── matplotlib/
└── xarray/
```

### `04_SQL/` *(planned)*
SQL practice — schema design, queries, window functions, and PostGIS spatial queries. Exercises built around climate and energy datasets.

### `05_Stats_and_Math/` *(planned)*
Statistics and mathematics for data science — probability, distributions, hypothesis testing, and linear algebra. Applied to climate data problems.

### `06_Machine_Learning/` *(planned)*
ML concepts and experiments — from regression to deep learning. Each subfolder covers one algorithm or technique with a climate-relevant dataset.

---

## How This Connects to Climate Projects

This repo and [Climate Projects](https://github.com/anujsharma-codex/Climate-Projects) are two sides of the same roadmap:

| Stage | What goes in Python Learning Journey | What goes in Climate Projects |
|---|---|---|
| Python + OOP | Fundamentals exercises + Solar Calculator | Solar Potential Calculator v1.0 |
| Libraries | Pandas/NumPy/Matplotlib/Xarray practice | Extreme Weather Event Analyzer |
| SQL | Schema exercises, query practice | Hydrometeorological Station Database |
| Stats & Math | Concept exercises | Climate Change Signal Detector |
| ML | Algorithm experiments | Dunkelflaute Predictor |

**Python Learning Journey** = the process, the practice, the learning in public

**Climate Projects** = the finished output, portfolio-ready and documented

---

## Goal

Every folder in this repo exists to build one thing: the ability to take raw climate data, apply physics-aware machine learning and statistical analysis, and turn it into risk intelligence that energy companies, insurers, and policymakers can act on.

This is the foundation. [Climate Projects](https://github.com/anujsharma-codex/Climate-Projects) is where it gets applied.
>>>>>>> c8b2be0bb890e985b7c50a9a76f4eb9025a1b12e
