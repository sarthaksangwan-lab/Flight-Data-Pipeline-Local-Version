# Flight Data Pipeline (Local Version)

### Description
Flight Data Pipeline fetches real time flight data from the Aviationstack API, transforms raw JSON into structured CSV, and stores it locally. It follows an ETL process and helps simulate real-world data engineering workflows without using cloud services.

![ETL Process](https://github.com/sarthaksangwan-lab/Flight-Data-Pipeline-Local-Version/blob/main/ETL%20Process.jpg)

### Prerequisites
**1**: Aviationstack API Key-- (https://aviationstack.com/signup/free) Use this link to create free acount and get your API Access Key. 

**2**: Install required packages:
    
    pip install requests pandas

## --- How This Project Works ---
This project is a simple local ETL (Extract, Transform, Load) pipeline for real-time flight data using the Aviationstack API. It runs in two main steps:

#### 1. Extract: Pull Real-Time Data from API
The extract.ipynb notebook connects to the Aviationstack API and fetches live flight data. Each time it runs, it stores the response as a new .json file in the raw/ folder with a timestamp in the filename.

#### 2. Transform: Clean and Structure the Data
The transform.ipynb notebook reads all raw .json files from the raw/ folder, extracts important fields (like airline, flight number, airports, scheduled time, and status), removes duplicates, and saves the cleaned data as a .csv file in the processed/ folder.

## --- Notes ---
**1) Replace the placeholder API key** in extract.ipynb with your own Aviationstack API Key:

    API_KEY = "your_actual_api_key"

**2) Update the file path** in extract.ipynb to point to your local raw data directory:  

    filename = "YOUR_RAW_FOLDER_PATH/raw/flights_{timestamp}.json"

**3) Update folder paths** in transform.ipynb to match your local setup:

    RAW_FOLDER = "YOUR_RAW_FOLDER_PATH/raw"
    PROCESSED_FOLDER = "YOUR_PROCESSED_FOLDER_PATH/processed"

**4) Run** extract.ipynb **first** to fetch real-time flight data and save it as raw .json files in the specified folder.

**5) Run** transform.ipynb **next** to read all raw .json files, process the flight data, remove duplicates, and save a clean .csv in the processed folder.

##### ***AND YOU'RE ALL SET!!***
