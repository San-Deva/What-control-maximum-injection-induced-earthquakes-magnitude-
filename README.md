# What controls maximum injection induced earthquakes magnitude?

This repository supports the study where we develop a **machine learning framework** to identify key physical features associated with the **maximum injection-induced moment magnitude** using a comprehensive geo-database.

---

## Dataset

We use the publicly available dataset:  
**GEoREST Induced Seismicity Database**  
[`GEoREST_induced_seismicity_database_v20.11.2022.xlsx`](https://digital.csic.es/handle/10261/284662)

This dataset includes a multiphysical dataset from 156 injection sites across various projects along with a supporting bibliography and dictionary provided at the same link.

---

## Methodology Overview

1. **Missing Data Imputation**
   - Script: `RandomForestRegressor_Numerical_V1.ipynb`
   - Used to impute missing numerical values, especially **Biot’s coefficient**.
   - Missing host rock properties are filled using **mean values from available literature**.

   Output:  
   `Mean_Rocksiteinjection.xlsx`  
   (used as input for modeling; main sheet: `Mean_all`)

2. **Exploratory Analysis**
   - Script: `Heat_Map_Script_V1.ipynb`
   - Generates heatmaps and computes **Pearson** and **Spearman** correlation matrices.
   - Assesses relationships between:
     - Host rock parameters  
     - Site-specific geological features  
     - Injection variables

    Selected features exported to new sheet: `Mean_rock`

3. **Model Training & Feature Importance**
   - Scripts: `LIGHTGBM_Script_V1.ipynb` and `LIGHTGBM_Script_V2.ipynb`
   - Use **LightGBM regression** to:
     - Plot validation curves  
     - Identify key predictive features
   - Outputs help interpret potential **triggering mechanisms** behind fluid injection–induced seismicity.



