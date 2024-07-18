# HOW TO USE THE CODE IN THIS REPO

First and foremost, install the dependencies in your conda environment:

`conda env update -n <your_env> --file environment.yaml`

## REPRODUCING GLORYS RESULTS

The two notebooks situated at the root of this github that can be used to reproduce testing results on OSE NRT (Near Real Time) data.

## 1st step: Downloading and Pre-Processing OSE data:

Use [the data pipeline notebook](../ose_data_pipeline.ipynb) in order to **download** and **pre-process** your desired data.
This notebook uses files situated in the [data](data) folder.

*2023 NRT and reprocessed altimetry data is already baked into this repository in the [data folder](../data/), which lets you skip this step altogether if you don't need to reproduce the results for different data*

## 2nd step: Using your trained 4DVarNet model and computing results

Use [the results reproducing notebook](../reproduce_glorys_ose_results.ipynb) in order to apply your **trained model** on the OSE data obtained during the **1st step**.
The reconstructed outputs will be compared with the OSE reference data and **metrics will be computed** for each present and future **leadtime**.

This notebook uses files situated in the [reproduce](reproduce) folder, and the code used to run the model (python files at the root of `src`) are directly coming from the [4DVarNet (forecast)](https://github.com/CIA-Oceanix/4dvarnet-starter/tree/forecast) repository.


---
*You're gonna carry that .pth*