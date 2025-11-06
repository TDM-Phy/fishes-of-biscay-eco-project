Marine Fish Abundance Investigation: Bay of Biscay and Algarve
Overview

This project investigates the drivers of marine fish abundance along the Atlantic coasts of France, Spain, and Portugal — from the Bay of Biscay to the Algarve.
It demonstrates a full data-science workflow: from sourcing and cleaning ecological data to integrating environmental variables, auditing dataset quality, and applying both statistical and machine-learning models.

The investigation is based on OBIS (Ocean Biodiversity Information System) occurrence data, enriched with environmental variables such as bathymetry, distance to shore, sea surface temperature (SST), and chlorophyll-a concentration (CHL).
While ecological insights are not explicitly interpreted, the notebooks showcase technical proficiency in data engineering, exploratory analysis, statistical modelling, and machine learning.

Repository Structure
Notebook	Description
01-Fish-data-collection.ipynb	Sets up filters and queries to download Bony Fish (Actinopterygii) records from the OBIS API, constrained to the Bay of Biscay–Algarve bounding box. Outputs a CSV for subsequent analysis.
02-Fish-data-cleaning-and-exploration.ipynb	Performs QA/QC checks on the fish dataset: removes incomplete records, visualises spatial and temporal sampling effort, and summarises key biological fields (family, sex, lifestage).
03-Env-Data-Extraction.ipynb	Integrates environmental covariates. Extracts both static variables (bathymetry, distance to coast) and dynamic variables (SST, CHL) from open-access gridded datasets using ERDDAP and GEBCO sources.
04-Auditing-and-statistical-investigation.ipynb	Conducts a full data audit ensuring integrity, consistency, and completeness. Defines analytical variables (region, month, family) and fits a Negative Binomial model to explore environmental effects on fish abundance as a classical statistical baseline.
05-ML-model-pipeline-species.ipynb	Applies both unsupervised and supervised machine-learning techniques at the species level. Unsupervised clustering identifies community groupings by environmental similarity. A Random Forest model is then trained and tuned to predict community presence, followed by Partial Dependence Plots (PDPs) to visualise the influence of continuous predictors.
figures/	Contains static figures, plots, and visual outputs generated throughout the analysis.

Methodological Summary

1. Data Collection: 

Source: OBIS occurrence data

Target taxon: Actinopterygii (bony fishes)

Study area: Bay of Biscay → Algarve

Output: CSV of filtered occurrences

2. Data Cleaning and QA/QC

Removal of missing coordinates and dates

Temporal and spatial visualisation of sampling effort

Initial summary statistics of biological fields

3. Environmental Variable Integration

Static: Bathymetry (GEBCO), distance to coast (Natural Earth)

Dynamic: SST (OISST via ERDDAP), CHL (Copernicus / CoastWatch)

4. Data Audit and Statistical Modelling

Validation of data integrity

Harmonisation of spatial and temporal formats

Definition of analysis variables

Negative Binomial GLM fitted to assess key drivers

5. Machine Learning Pipeline

Unsupervised: Community identification and clustering

Supervised: Random Forest classification predicting community presence

Model evaluation and hyperparameter tuning

Partial Dependence Plots to interpret predictor effects

Dependencies

All required packages are listed in the project’s environment.yml (or alternatively requirements.txt).
Core libraries include:

pandas, numpy, matplotlib, seaborn

geopandas, rasterio, shapely

xarray, netCDF4

scikit-learn, statsmodels

requests, tqdm

Author

Theo Murphy
Marine Ecologist & Data Scientist
Bay of Biscay Eco-Project | 2025