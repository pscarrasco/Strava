# Strava
Data Analysis on Strava activities

## Project Overview
This project pulls all of my Strava-recorded activities from January 2024 through mid-May 2025, then turns that raw JSON into actionable training insights:
#### Data Acquisition
OAuth 2.0 flow exchanges a short-lived authorization code for an access token.
A paginated loop queries the Strava v3 /athlete/activities endpoint until every activity is retrieved.

#### Data Cleaning & Harmonization

Converts the nested JSON into a tidy pandas DataFrame.

Normalizes inconsistent labels (e.g., WeightTraining → Weight Training, HighIntensityIntervalTraining → HIIT).

Calculates derived fields (pace, month, year-month) for time-series analysis.

#### Geospatial Enrichment

Decodes Google-encoded polylines for each run.

Filters coordinates inside a Cuenca bounding box to isolate local training routes.

#### Exploratory Analysis & Visualization

Heat-map pinpoints the streets and trails I use most often.

Pie / bar charts reveal how much time I devote to running vs. strength, HIIT, and cycling.

Line charts track month-over-month progress in total runs and kilometers.

#### Performance Summary

Computes headline stats for runs—average heart-rate, distance, elevation gain, typical pace, total kilometers, and run count—offering a quick snapshot of current fitness.

#### Reproducibility & Extensibility

A standalone strava_analysis.py script (and matching Jupyter notebook) make reruns easy after future workouts.

## Technologies Used
- Python
- Pandas
- Matplotlib
- Strava v3 API

## Getting Started
To run the analysis locally, follow these steps:
1. Clone the repository:
   git clone https://github.com/pscarrasco/Strava.git
2. Install the required dependencies:
   pip install -r requirements.txt
3. Open the Jupyter Notebook file.
4. Run the project.
