# NASA DONKI API: Coronal Mass Ejection and Geomagnetic Storm Analysis

## Project Overview
This project analyzes the relationship between Coronal Mass Ejections (CMEs) and Geomagnetic Storms (GSTs) using data from NASA's DONKI (Database Of Notifications, Knowledge, and Information) API. The goal is to prepare a dataset that can be used to predict when Geomagnetic Storms will occur based on observed CMEs from the sun.

## Background
Coronal Mass Ejections (CMEs) are massive bursts of plasma emitted from the Sun that can interact with Earth's magnetic field, causing Geomagnetic Storms (GSTs). These storms can impact satellites, GPS systems, power grids, and other electronic infrastructure.

The NOAA Space Weather Prediction Center uses data on CMEs to predict when GSTs might occur, allowing operators of sensitive electronic systems to take precautionary measures. This project helps with the data preparation phase of building such a prediction system.

## Data Source
The data is retrieved from NASA's DONKI API, which provides access to space weather event data. The API documentation can be found at: https://api.nasa.gov/

The specific endpoints used in this project are:
- `/DONKI/CME` - For Coronal Mass Ejection data
- `/DONKI/GST` - For Geomagnetic Storm data

## Key Findings

Based on the analysis of CME and GST data from 2013 to 2024:

1. **Average Travel Time**: On average, it takes approximately 2 days and 21 hours for a CME to travel from the Sun to Earth and cause a Geomagnetic Storm.

2. **Travel Time Range**: The minimum travel time observed was about 1 day and 5 hours, while the maximum was about 6 days and 3 hours.

3. **Standard Deviation**: There is a standard deviation of about 1 day in the travel times, indicating moderate variability in how quickly CMEs impact Earth.

4. **Median Travel Time**: The median travel time is approximately 2 days and 17 hours, slightly less than the mean, suggesting some positively skewed distribution (a few unusually long travel times).

## Project Structure

- `retrieve_data.ipynb`: Jupyter notebook containing the code to retrieve, process, and analyze the data
- `cme_gst_data.csv`: Output file containing the merged and processed data
- `.env`: Environment file containing the NASA API key (not included in repository)
- `README.md`: This file, providing an overview of the project

## Setup and Usage

1. **Clone the repository**:
2. **Set up your API key**:
- Obtain a NASA API key from https://api.nasa.gov/
- Create a `.env` file in the project directory
- Add your API key to the file: `NASA_API_KEY=your_api_key_here`

3. **Install required dependencies**:
4. **Run the Jupyter notebook**:
   5. **View the results**:
- The processed data will be saved to `cme_gst_data.csv`
- Key statistics about travel time are displayed in the notebook

## Data Dictionary

The final dataset (`cme_gst_data.csv`) contains the following columns:

- `gstID`: Unique identifier for the Geomagnetic Storm
- `startTime_GST`: Timestamp when the Geomagnetic Storm was observed
- `CME_ActivityID`: Identifier for the Coronal Mass Ejection linked to the storm
- `cmeID`: Unique identifier for the Coronal Mass Ejection
- `startTime_CME`: Timestamp when the Coronal Mass Ejection was observed
- `GST_ActivityID`: Identifier for the Geomagnetic Storm linked to the CME
- `timeDiff`: Time difference between the CME and GST observations (travel time)

## Conclusions and Potential Applications

The data prepared in this project can be used to:

1. **Train prediction models** that forecast when Geomagnetic Storms might occur based on observed CMEs
2. **Establish early warning systems** for power grid operators, satellite controllers, and other stakeholders
3. **Study patterns** in space weather events over time
4. **Analyze the characteristics** of CMEs that cause the most significant Geomagnetic Storms

By better understanding the relationship between these space weather phenomena, we can improve our ability to mitigate their impacts on Earth's technological infrastructure.

## Acknowledgments

- NASA for providing the DONKI API and data
- NOAA Space Weather Prediction Center for their research and forecasting work
