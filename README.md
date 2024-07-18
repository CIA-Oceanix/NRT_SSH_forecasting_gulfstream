# NRT_SSH_forecasting_gulfstream

## Goals

Performing forecasts on recent NRT (Near Real-Time) SSH (Seas Surface Height) data using the 4DVarNet model, we evaluate different methods of training for ocean sea surface forecasting. This study so far only extends to a region of the gulfstream.

## Datasets

1. **NRT** Dataset: Near-Real Time Altimetry data along tracks of multiple satellites, to be found on the [CMEMS portal](https://data.marine.copernicus.eu/product/SEALEVEL_GLO_PHY_L3_NRT_008_044/description)
2. **Reprocessed** Dataset: Similar to the NRT Dataset, this data has been reprocessed with data from the past and the future, filtered to best represent the real state of the ocean along the satellite tracks. Can be found on the [CMEMS portal](https://data.marine.copernicus.eu/product/SEALEVEL_GLO_PHY_L3_MY_008_062/description).
3. **Glorys12** Dataset: This Dataset contains Altimetry data gridded for the whole ocean. Found on the [CMEMS portal](https://data.marine.copernicus.eu/product/GLOBAL_MULTIYEAR_PHY_001_030/description).

## Code

The code used for experiments and its description can be can be found in the [src folder](src/).

If you mean to use this notebook, dependencies and explanations are situated in this folder as well.

## First experiment: Glorys12 training

The model used is **4DVarNet**-forecast trained on **Glorys12** data over a period of 10 years (2010-2019).

### Test over 2022

#### Data

- Test data input: **NRT** data over the year 2022
- Test data reference: **NRT** data over the year 2022

| leadtimes (days) | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
|---|---|---|---|---|---|---|---|
| **µ(RMSE)**| 0.882 | 0.860 | 0.849 | 0.829 | 0.814 | 0.806 | 0.783 |

### Test over 2023

#### Data

- Test data input: **NRT** data over the year 2023
- Test data reference: **Reprocessed** data over the year 2023

| leadtimes (days) | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
|---|---|---|---|---|---|---|---|
| **µ(RMSE)**| 0.796 | 0.772 | 0.725 | 0.702 | 0.660 | 0.669 | 0.597 |
