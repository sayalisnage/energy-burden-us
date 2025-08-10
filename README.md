# Quantifying Energy Burden in the United States
### A State-Level Assessment of Electricity Affordability and Climate Impact

This project investigates the energy burden—the percentage of household income spent on electricity across the United States from 2021 to 2023. Leveraging a unified dataset from the U.S. Energy Information Administration, the U.S. Census Bureau, and the National Oceanic and Atmospheric Administration, this analysis aims to quantify regional disparities, identify key drivers, and provide a foundation for policy interventions aimed at improving energy equity.

---

## Project Overview

Energy burden disproportionately affects low-income households and is a critical indicator of energy affordability. This study combines economic, energy, and climate data to produce a comprehensive state-level analysis. The findings provide insights into the socio-economic and environmental dimensions of household energy affordability, which can inform policymakers, researchers, and advocacy groups working toward a more equitable energy landscape.

---

## Data Sources

* __U.S. Energy Information Administration (EIA):__ Monthly residential electricity prices, sales, and customer counts for each U.S. state for the years 2021-2023.
    * Source: [https://www.eia.gov/electricity/data.php#revenue](https://www.eia.gov/electricity/data.php#revenue)
* __U.S. Census Bureau, American Community Survey (ACS):__ Annual median household income data for each U.S. state for the years 2021-2023.
    * Source: [https://www.census.gov/](https://data.census.gov/table/ACSST1Y2023.S1903?q=Median+Household+Income)
* __National Oceanic and Atmospheric Administration (NOAA):__ Monthly monthly average temperature and Cooling Degree Days (CDD) for each U.S. state for the years 2021-2023.
    * Source: [https://www.noaa.gov/](https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/statewide/time-series/service-api)

---

## Methodology

1.  __Data Collection and Preprocessing:__ Initial acquisition of raw datasets, including exploratory data analysis to understand structure, formats, and coverage.
2.  __Data Cleaning & Preparation:__ Standardized state names, date formats, and units (e.g., MWh to kWh). Annual income data was aligned with monthly energy data to create a unified panel.
3.  __Energy Burden Calculation:__ The central metric, `Energy Burden (%)`, was derived as the ratio of household electricity cost to median household income for each state and time period.
4.  __Exploratory Data Analysis (EDA):__ Visualized state-level prices, climate distributions, and the relationship between income and affordability to identify key patterns and regional disparities.
5.  __Statistical Modeling & Interpretability:__ Employed regression analysis and SHAP (SHapley Additive exPlanations) values to identify and quantify the influence of key drivers on the energy burden, such as income, price, and climate.

---

## Technology Stack

* __Programming Language:__ Python
* __Libraries & Tools:__
    * __Data:__ Pandas, NumPy
    * __Visualization:__ Matplotlib, Seaborn, Plotly
    * __Modeling:__ Scikit-learn, Statsmodels, SHAP
    * __Development:__ Jupyter Notebooks, Git

---

## How to Run the Project

To set up and run this project locally, follow these steps:

1. __Clone the repository:__
    ```bash
    git clone https://github.com/[sayalisnage]/energy-burden-us.git
    cd energy-burden-us
    ```

2. __Create a virtual environment (recommended):__
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. __Install required dependencies:__
    ```bash
    pip install -r requirements.txt
    ```

4. __Acquire Raw Data:__
    * __EIA Data__ – Download directly from the EIA website in CSV format and place in `data/raw/eia/`.
    * __ACS Data__ – Download directly from the U.S. Census Bureau (ACS) website in CSV format and place in `data/raw/acs/`.
    * __NOAA Climate Data__ – Requires an API key from NOAA’s NCEI.
        - Sign up at [https://www.ncei.noaa.gov/support/access-search-service-api-user-documentation](https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/statewide/time-series/service-api) to obtain your API key.
        - Place your API key in a `.env` file as:
          ```
          NOAA_API_KEY=your_api_key_here
          ```
        - Run the data acquisition script to fetch climate data:
          ```bash
          python scripts/data_acquisition/noaa_data_acquisition.py
          ```

5. __Preprocess NOAA Data:__
    * Run the preprocessing script to clean and combine all datasets:
      ```bash
      python scripts/noaa_data_preprocessing.py
      ```
    * Processed data will be saved into the `data/processed/` directory.

6. __Prepare, Explore and Analyze Data in Jupyter:__
    * Launch Jupyter Notebook or JupyterLab:
      ```bash
      jupyter notebook
      ```
    * Navigate to the `notebooks/` directory and open `energy_burden_analysis.ipynb`.
    * Execute the cells sequentially to perform:
      - Exploratory Data Analysis (EDA)
      - Data visualization
      - Energy burden calculations
      - Modeling and evaluation
---

## Results Summary

* Energy burden is disproportionately high in Southern states, driven by a combination of lower median incomes and high cooling demands.
* Median household income is the strongest negative driver of energy burden, meaning higher incomes are most effective at reducing the burden.
* Electricity price and climate metrics (e.g., average temperature and Cooling Degree Days) are significant positive drivers.
* The relationships between these variables and energy burden are largely linear and predictable.

---

## Future Work

* Expand dataset coverage to include more years (e.g., a 5-10 year period) for robust trend analysis.
* Integrate granular data on home characteristics, such as housing age and insulation, to better account for energy efficiency.
* Develop advanced predictive models to forecast energy burden under different climate and economic scenarios.

---

## Contact

## Contact

For questions or collaboration, please reach out via [E-mail](sayalinage@gmail.com) or connect on [LinkedIn](https://www.linkedin.com/in/sayali-nage-34303b136/).

---
