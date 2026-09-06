# ASG AIRLINES✈️

## About the Project

This is my airline data analysis project called **ASG AIRLINES**.

The main aim of this project is to take airline data, clean it, find problems in the data, and then use the cleaned data to make useful analysis and a Power BI dashboard.

I used **Python, Pandas, Jupyter Notebook and Power BI** for this project.

---

## What is included in the project?

The project mainly contains data about:

* ✈️ Flights
* 🎫 Bookings
* 💳 Payments
* 👤 Passengers

The original data was given in an Excel file. I first loaded the data into Python and checked it for different problems like missing values, duplicate records and incorrect data.

After cleaning the data, I created separate files which can be used for analysis and Power BI.

---

## Project Flow

The project works roughly like this:

```text
Raw Airline Data
       ↓
Read the data
       ↓
Check the data
       ↓
Clean the data
       ↓
Find anomalies
       ↓
Create useful tables
       ↓
Create KPIs
       ↓
Power BI Dashboard
```

---

## Tools Used

### Python 🐍

Python was used for loading, cleaning and analysing the data.

### Pandas

I used Pandas to work with the tables and perform operations like:

* Removing/handling incorrect data
* Checking missing values
* Finding duplicates
* Changing data types
* Creating new columns
* Calculating statistics

### Jupyter Notebook

The complete data processing and analysis is done in the notebook:

```text
notebooks/airlines_pipeline.ipynb
```

### Power BI

Power BI was used to create the final dashboard and show the results in a more visual way.

---

## Folder Structure

```text
Neo Stats/
│
├── data/
│   ├── raw/
│   │   ├── UseCase - Airlines.xlsx
│   │   └── flights_ingested.csv
│   │
│   └── processed/
│       ├── clean_flights.csv
│       ├── clean_bookings.csv
│       ├── clean_payments.csv
│       ├── clean_passengers.csv
│       ├── flight_anomalies.csv
│       ├── passenger_anomalies.csv
│       │
│       └── powerbi/
│           ├── fact_flights.csv
│           ├── fact_bookings.csv
│           ├── fact_payments.csv
│           ├── dim_airline.csv
│           ├── dim_route.csv
│           ├── dim_date.csv
│           └── dim_passenger.csv
│
├── logs/
│   └── pipeline.log
│
├── notebooks/
│   └── airlines_pipeline.ipynb
│
├── Power bi/
│   └── Airlinde_dashboard.pbix
│
└── README.md
```

---

## What I did in the project

### 1. Loading the Data

First, I loaded the airline Excel file into Python.

I checked the different sheets and looked at what type of information was present in each one.

---

### 2. Checking the Data

Before cleaning the data, I checked for things like:

* Missing values
* Duplicate IDs
* Incorrect dates
* Incorrect flight duration
* Invalid payment values
* Problems between different tables

This helped me understand what problems were present in the original dataset.

---

### 3. Cleaning Flight Data

For the flight data, I cleaned things such as airline names, airport codes and dates.

I also calculated the flight duration and created some additional columns that are useful for analysis.

I also checked whether the arrival time made sense compared to the departure time.

For example, some records had incorrect timestamps. These were marked as anomalies instead of just being ignored.

---

### 4. Handling Duplicate Flights

There was a duplicate flight ID called **6F250**.

Instead of simply deleting one of the rows, I checked the records properly. The two records had different route information, so I treated them as an issue that needed to be flagged.

I think this is better than deleting data without checking why it is duplicated.

---

### 5. Bookings and Payments

I also cleaned the booking and payment data.

For bookings, missing or incorrect booking statuses were handled and flagged.

For payments, invalid amounts were not changed to zero because that would give incorrect financial information. They were instead marked as missing/invalid.

---

### 6. Passenger Data

The passenger data contains personal information.

Since the dashboard does not need information like phone numbers, email addresses or exact dates of birth, I did not include unnecessary personal information in the final analytical data.

I mainly used information such as:

* Passenger ID
* Gender
* Age Band

This makes the dataset safer while still allowing passenger analysis.

---

## Some Data Problems Found

During the project, I found different types of problems in the original data.

Some examples are:

* Duplicate flight IDs
* Incorrect timestamps
* Invalid flight durations
* Missing booking status
* Invalid payment amounts
* Passenger ID problems
* Records that do not match between tables

I created separate **anomaly files** so these problems can still be seen instead of simply deleting them.

---

## Main Results

After cleaning the data, I got the following results:

| Information             |        Result |
| ----------------------- | ------------: |
| Clean Flights           |         1,004 |
| Flight Anomalies        |             3 |
| Airlines                |             4 |
| Routes                  |            30 |
| Bookings                |         1,000 |
| Payments                |         1,000 |
| Clean Passengers        |           964 |
| Passenger Anomalies     |            75 |
| Average Flight Duration | 164.5 minutes |

### Flights by Airline

| Airline   | Flights |
| --------- | ------: |
| IndiGo    |     273 |
| Air India |     255 |
| SpiceJet  |     246 |
| Vistara   |     230 |

The route with the highest number of flights was **BOM → CCU**, with 90 flights.

---

## KPIs

Some of the main KPIs calculated in the project are:

* Total Flights
* Total Airlines
* Average Flight Duration
* Route-wise Flight Traffic
* Flight Anomalies
* Flights by Airline

I also looked at some extra information such as:

* Booking status
* Payment information
* Passenger gender
* Passenger age groups
* Overnight flights

---

## Power BI Dashboard

After preparing the data, I used the processed files in Power BI.

The Power BI file is:

```text
Power bi/Airlinde_dashboard.pbix
```

The dashboard helps show the data using charts and KPIs instead of only looking at tables.

The Power BI data is organised into fact and dimension tables.

### Fact Tables

* `fact_flights`
* `fact_bookings`
* `fact_payments`

### Dimension Tables

* `dim_airline`
* `dim_route`
* `dim_date`
* `dim_passenger`

This makes it easier to connect the different types of data in Power BI.

---

## How to Run the Project

To run the Python part of the project, Python needs to be installed.

The main libraries used are:

```bash
pip install pandas openpyxl jupyter
```

Then open Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
notebooks/airlines_pipeline.ipynb
```

and run the notebook cells from beginning to end.

The processed files will be created inside:

```text
data/processed/
```

The Power BI files are available inside:

```text
data/processed/powerbi/
```

---

## What I Learned

While doing this project, I learned how raw data can have many problems even when it looks normal at first.

I learned how to:

* Read Excel data using Python
* Use Pandas for data cleaning
* Find missing and duplicate data
* Work with dates and times
* Find unusual records
* Create new columns
* Calculate KPIs
* Organise data into fact and dimension tables
* Prepare data for Power BI
* Make a dashboard from cleaned data

One important thing I learned is that **we should not just delete data when we find something unusual**. We should first understand what the problem is and then decide how to handle it.

---

## Conclusion

Overall, this project helped me understand the complete process of working with data — from the original Excel file to a cleaned dataset and finally to a Power BI dashboard.

The main idea of the project was not only to make a dashboard, but also to make sure that the data being used in the dashboard was checked and cleaned properly.

**Thank you for checking out my project!** ✈️
