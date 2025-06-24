<img width="1139" alt="image" src="https://github.com/user-attachments/assets/b5127c42-12e0-4e1f-8ad6-8497c81eaf46" />

## Project Overview

This project analyzes time series data from Barcelona’s public bike-sharing system (Bicing) to forecast hourly bike availability at the station level.  
The original dataset, spanning from 2019 to 2024, includes mechanical and electric bike counts updated every 4 minutes.  
The data is resampled to hourly intervals to enable scalable processing and forecasting for mobility planning and operational optimization.

## Objectives

- Integrate and preprocess Bicing station datasets from monthly CSV files  
- Resample raw 4-minute data into consistent hourly time series  
- Clean and unify features related to bike types and station activity  
- Engineer features using date, time, and holiday metadata  
- Prepare time series for future modeling and predictive forecasting  
- Visualize bike availability, usage trends, and station-level variability  
- Generate station activity maps using Folium

## Tools and Libraries

- Python 3.x  
- pandas  
- numpy  
- seaborn  
- folium  
- tqdm  
- pathlib  
- datetime and holidays modules  
- scikit-learn (for scaling)

## Project Structure

barcelona-bicing-timeseries-analysis/  
├── bicing_hourly_availability_forecasting.ipynb   – Main analysis and processing notebook  
├── 2021_*_STATIONS_hourly_mean.csv                – Monthly Bicing data files (hourly resampled)  
├── 2021_INFO.csv                                  – Station-level metadata  
├── README.md                                      – Project documentation  

## Dataset Description

- Source: [Barcelona Open Data Bicing APIs](https://opendata-ajuntament.barcelona.cat/en/)  
- Station data: Hourly average availability of bikes and docks  
- Station info: Location, operational status, renting flags  
- Fields used:
  - date  
  - station_id  
  - num_bikes_available  
  - num_bikes_available_types.mechanical  
  - num_bikes_available_types.ebike  
  - num_docks_available  
  - is_renting  
  - last_reported  

## Key Processing Steps

1. Loop over all relevant station files (e.g. 2021_01_STATIONS_hourly_mean.csv)  
2. Parse dates and restrict to a target time window  
3. Concatenate and clean across months  
4. Incorporate metadata and filter inactive stations  
5. Engineer date/time features (hour, day, weekday, holiday flags)  
6. Visualize trends using seaborn and create map overlays with Folium

## How to Run

1. Place all monthly station CSV files and station info files in the root directory  
2. Open the notebook `bicing_hourly_availability_forecasting.ipynb`  
3. Install dependencies using:  
   pip install pandas numpy seaborn folium tqdm scikit-learn holidays  

4. Run the cells sequentially to preprocess, visualize, and export aggregated data

## Requirements

Install dependencies using:  
pip install pandas numpy seaborn folium tqdm scikit-learn holidays

## License

This project is licensed under the MIT License. See the LICENSE file for details.
