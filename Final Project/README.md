**NYC Rent Policy Analysis – MSDS 607 Final Project**

This project analyzes Manhattan rent trends using **Zillow ZORI** and **HUD Fair Market Rent (FMR)** data, and models how different policy scenarios (free market, rent stabilization, and rent freeze) might affect future rent levels. The goal is to compare a projected 2030 “free-market” rent path with regulated alternatives to understand potential impacts on affordability.

**Data Sources**

**Zillow ZORI (ZIP-level monthly rent index)**
  File: `Zip_zori_uc_sfrcondomfr_sm_month.csv`
  Used to compute annual average ZORI values for Manhattan.

**HUD Fair Market Rents (1983–2026)**
  Files:

  * `FMR_All_1983_2026.csv` (original)
  * `hud_manhattan_fmr_1983_2026.csv` (cleaned subset used in analysis)
    Used to obtain Manhattan’s annual 1BR Fair Market Rent.

**Methods**

* Cleaned and merged ZORI + HUD datasets
* Converted wide-format ZORI data into long format and aggregated to annual values
* Fit a linear model estimating annual rent growth (≈ **$124 per year**, R² = **0.955**)
* Created 2030 projections under:

  * **Free market**
  * **1% rent stabilization**
  * **Rent freeze**
* Added a geospatial map feature using `{sf}` and `{tigris}`


**Key Results**

| Scenario         | 2030 Projected Rent |
| ---------------- | ------------------- |
| Free market      | **$3,043**          |
| 1% stabilization | **$2,602** (–14.6%) |
| Rent freeze      | **$2,451** (–19.5%) |

Rent regulation scenarios show substantially slower rent growth compared with an unregulated path.


**Reproducibility**

To run the analysis:

1. Open `data607_final.Rmd` in RStudio
2. Ensure data files remain in the `data/` folder
3. Required packages: `tidyverse`, `janitor`, `lubridate`, `broom`, `sf`, `tigris`, `scales`


Let me know if you want an even shorter (5–6 line) README or a polished version for grading!

