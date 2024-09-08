# The task's purpose
The project will process and document the forecasting track and the trading track of the Hybrid Energy Forecasting and Trading Competition, with the focus on the forecasting track. To do this, the typical process steps of a data science project will be completed. This first involves understanding the problem. The basis for this is the documentation provided by the competition and, if applicable, the sources referenced therein. Please use the Internet to find out more about the topic of electricity markets. A thorough preparatory data analysis and comprehensible documentation of the procedure are also part of the project.

In this Readme file I will present the first two phases of `CRISP-DM` [Cross-industry standard process for data mining] and part of the 3rd pahse:
* Business understanding
* Data understanding
* Data preparation

## Business Understnading
Forecasting production from wind and solar power plants, and making effective decisions under forecast uncertainty, are essential capabilities in low-carbon energy systems.

## Data Undestanding
Data is taken from [IEEE](https://ieee-dataport.org/competitions/hybrid-energy-forecasting-and-trading-competition) competition.
It contains:
* 21 `.nc` files
* 2 `.csv` files.

The .nc files extension represent weather data and .csv files represent enertgy data.
Overall time period: 2020-09-20 to 2024-05-19: 1342 days (or 3 years and 243 days).

### Weather Data

The .nc files extension represent weather data and gives us data about windmills (wind speed, wind direction, temperature, RelativeHumidity) and solar panels (Cloud cover, solar downward radiation and temperature).
Weather data is given from 2 sources: **Deutsches Wetterdienst** and **Global Forecast System**.

I will use 8 .nc files and 2 .csv files.
.nc extension filename means it's a NetCDF [Network Common Data Form] files. In order to use it, a package of NetCDF must be installed.
In order to read the data, I will use Xarray. Xarray bundles a backend for this format. Xarray introduces labels in the form of dimensions, coordinates and attributes on top of raw NumPy-like multidimensional arrays.

### Energy Data

The energy data has several important features like `dtm`, `MIP`, `Solar_MW`, `Solar_capacity_mwp`, `Solar_installedcapacity_mwp`, `Wind_MW`, `SS_Price`, `boa_MWh`,
       `DA_Price`, `Wind_MWh_credit` and `Solar_MWh_credit`.



## Data Perparation

This section contains data cleaning, setting columns types and Exploratory data Analysis (EDA). Currently, onlt plots and fidures will be presented with no code.

My main inspiration comes from the [Getting Started Notebook](https://github.com/jbrowell/HEFTcom24/blob/main/Getting%20Started.ipynb) that was presented at the competition

After creating the modelling table I wanted to reduce the memory of the dataframe.
* Before: &nbsp 3
<p align="center">
  <img src="https://i.imgur.com/O9Gp9ox.png" width="450"/>
  <img src="https://i.imgur.com/kvRwmWH.png" width="450"/>
</p>
