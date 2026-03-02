# Solar Potential Calculator

![Version](https://img.shields.io/badge/version-1.0.0-green) ![Python](https://img.shields.io/badge/python-3.x-blue) ![Libraries](https://img.shields.io/badge/libraries-none-lightgrey)

A command-line tool to evaluate solar panel installation viability for residential and commercial properties in India. Built using **pure Python and OOP** — no external libraries.

This is **Version 1.0** and **Phase 1** of my learning roadmap toward climate physical risk intelligence. The goal was to translate real-world domain logic (solar insolation, Indian subsidy structures, commercial tax incentives) into clean, object-oriented Python before introducing any data science libraries.

---

## Version History

| Version | Description | Status |
|---|---|---|
| **v1.0** — Pure Python + OOP | CLI tool with static city data, residential and commercial finance calculations | ✅ Current |
| **v2.0** — Real Climate Data | Replace static peak-sun-hours with ERA5/NSRDB hourly irradiance; pandas and xarray | 🔄 Planned |
| **v3.0** — Database Backend | PostgreSQL database for multi-city data; PostGIS spatial queries | ⏳ Planned |
| **v4.0** — Statistical Rigour | NPV/IRR calculations; bootstrapped confidence intervals on payback estimates | ⏳ Planned |
| **v5.0** — Forecasting | ML model predicting daily generation from atmospheric variables | ⏳ Planned |

---

## What It Does (v1.0)

Takes user inputs about location, panel specs, and roof dimensions, then calculates:

**For residential users:**
- Gross installation cost and net investment after government subsidy
- Monthly and annual savings based on electricity slab rate
- Payback period, total lifetime cost, LCOE, and lifetime savings per unit

**For commercial users:**
- Base system cost, GST amount, and gross cash outflow
- Net investment after accelerated depreciation tax shield and GST input credit
- Annual savings from working-day consumption and off-day grid export
- Net annual savings and payback period

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/yourusername/climate-projects.git
cd climate-projects/01_solar_calculator

# No dependencies to install — pure Python 3
python main.py
```

The program walks you through inputs interactively. Press **Enter** at any prompt to exit.

---

## Sample Session

```
WELCOME TO SOLAR POTENTIAL CALCULATOR

TELL ME ABOUT YOU

What type of user are you?
  1. Residential
  2. Commercial
  (Enter 1 or 2, or press ENTER to stop): 1

NOW TELL ME ABOUT YOUR LOCATION

Enter your city name  : Mumbai
Enter your state name : Maharashtra

NOW TELL ME ABOUT YOUR SOLAR PANEL!

Panel wattage (1=1kW, 2=2kW, 3=3kW, 4=4kW, 5=5kW): 3
Number of panels          : 10
Panel length in metres    : 2
Panel width in metres     : 1

NOW TELL ME ABOUT YOUR ROOF DIMENSIONS

Roof length in metres : 10
Roof width in metres  : 8
Enter your electricity slab rate (just the % number): 6

==================================================
MAIN MENU — SELECT A CATEGORY
==================================================
  1. SOLAR SYSTEM
  2. ENERGY GENERATION
  3. FINANCE
```

---

## Project Structure

```
01_solar_calculator/
│
├── main.py                     # CLI entry point, menu logic, factory functions
├── config.py                   # All constants: tariffs, subsidies, panel specs, city data
│
└── Solar/
    ├── __init__.py
    ├── solarcalculator.py      # SolarSystem and EnergyGeneration classes
    ├── location.py             # Location class — city/state lookup for tariffs and subsidies
    ├── financialcalculator.py  # ConsumerCategory, Residential, Commercial,
    │                           # ResidentialFinance, CommercialFinance classes
    └── utils.py                # Utils class — formatting, safe division, normalisation
```

---

## OOP Design

The class hierarchy is deliberately split by responsibility:

| Class | Responsibility |
|---|---|
| `SolarSystem` | Physical properties — panel area, feasibility check |
| `EnergyGeneration` | Energy calculations — daily, monthly, annual output |
| `Location` | Location-specific lookups — peak sun hours, tariffs, subsidies |
| `ConsumerCategory` → `Residential` / `Commercial` | User profile and config values per consumer type |
| `ResidentialFinance` / `CommercialFinance` | Financial calculations per consumer type |
| `Utils` | Shared helpers — string normalisation, currency formatting, safe divide |

`Residential` and `Commercial` both inherit from `ConsumerCategory`. The finance classes are intentionally separate rather than sharing a base class — residential finance is subsidy-driven while commercial finance is structured around GST and accelerated depreciation, which are fundamentally different cost models.

---

## Data Coverage (v1.0)

Currently supports **9 Indian cities**:

| City | State |
|---|---|
| Ahmedabad | Gujarat |
| Dehradun | Uttarakhand |
| Delhi | Delhi |
| Kolkata | West Bengal |
| Hyderabad | Telangana |
| Chennai | Tamil Nadu |
| Mumbai | Maharashtra |
| Indore | Madhya Pradesh |
| Jaipur | Rajasthan |

Subsidy data based on PM Surya Ghar Yojana combined central + state figures. Tariff data reflects 2024 state electricity board rates. Peak sun hours sourced from MNRE solar radiation data.

*v2.0 will replace this static table with real hourly irradiance data pulled from ERA5 or NSRDB, covering all of India.*

---

## Known Limitations (v1.0)

These are documented constraints, not omissions. Each one is a target for a future version:

**Static data** — Tariffs, subsidies, and market rates are hardcoded in `config.py`. They change regularly at state and central level. *v2.0 will load these dynamically.*

**Simplified energy model** — `calculate_daily_energy()` uses one peak-sun-hours constant per city. No seasonality, shading, dust losses beyond performance factor, or panel degradation. *v2.0 will use hourly irradiance data.*

**No city validation** — If a user types "Bombay" instead of "Mumbai", lookups silently return 0. *v2.0 will add fuzzy matching and explicit warnings.*

**Flat slab rate** — Real residential billing in India is tiered. This version assumes a single average rate entered by the user. *v4.0 will model tiered billing.*

**No time value of money** — Payback period is calculated without discounting future savings to present value. NPV and IRR would be more financially rigorous. *v4.0 will add discounted cash flow analysis.*

**Commercial self-consumption assumption** — Assumes 100% of daily generation is consumed on working days. *v5.0 will model actual load profiles.*

---

## Reflection

**What I assumed:** A single performance factor (0.75) and one peak-sun-hours value per city is a workable first approximation. For decisions spanning 25 years, this is a significant simplification — but the right one for a version built without data libraries.

**Where this approach fails:** The payback period doesn't discount future savings. A system that pays back in 4 years at 0% discount rate looks meaningfully different at a 10% discount rate. This is the most important financial limitation of v1.0.

**What building this taught me:** Separating physical, geographic, and financial logic into distinct classes made the code easier to extend and debug. The same separation-of-concerns principle will carry into every future version — even when the energy model becomes an ML forecast and the finance layer adds probabilistic uncertainty bounds.

---

## Upcoming in v2.0

- Replace static `CITY_PEAK_SUN_HOURS` dict with real ERA5 reanalysis data using `xarray`
- Add seasonal variation — monthly generation profiles instead of a single daily average
- Expand city coverage beyond 9 cities using PVGIS or NSRDB API
- Add pandas-based data cleaning pipeline for tariff and subsidy data
- Visualise monthly savings vs. loan repayment over panel lifetime using matplotlib

---

## Author

Built as Phase 1 of a climate physical risk intelligence learning roadmap — demonstrating algorithmic thinking and OOP design in a domain-relevant context, before introducing external libraries.
