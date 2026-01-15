# Data Wrangling & Exploratory Data Analysis of Spotify Data (2023-2024)

1. Project Information
Title: Data Wrangling & Exploratory Data Analysis of Spotify Data (2023-2024)

Authors: Bima Setia Sugiharto & Sholikin

Objective: This project aims to merge, clean, and analyze popular Spotify track datasets from 2023 and 2024. through data cleaning processes (such as removing irrelevant columns, handling missing values, and detecting outliers) and data visualization, this project provides insights into music trends, stream distributions, and artist performance on the streaming platform.

2. System Requirements
Ensure your Python environment has the following libraries installed:

pandas: For data manipulation.

numpy: For numerical operations.

matplotlib & seaborn: For data visualization.

Required input files (must be in the same directory as the script):

spotify-2023.csv

spotify-2024.csv

3. Code Workflow
A. Setup & Data Loading
The code begins by importing necessary libraries and loading the datasets.

Action: Run the initial cells to load pandas and read the CSV files using encoding='latin-1' to handle special characters correctly.

B. 2023 Data Cleaning
Column Selection: Technical audio features (like bpm, key, danceability_%, etc.) are dropped to focus on popularity metrics.

Renaming: Columns are renamed for consistency (e.g., track_name to track).

Formatting: Commas are removed from numeric strings (e.g., "1,000" becomes 1000) and converted to float data types.

Handling Missing Values: Missing (NaN) values in numeric columns (like streams) are filled using the median value.

Date Standardization: Year, month, and day columns are combined into a single datetime object.

C. 2024 Data Cleaning
Column Selection: Irrelevant columns (like TikTok Posts, Soundcloud Streams, etc.) are dropped to align with the 2023 data structure.

Date Extraction: Year, month, and day are extracted from the Release Date column.

Format Matching: Column names are mapped to match the 2023 dataset to facilitate merging.

D. Data Integration
Concatenation: Uses pd.concat() to merge the 2023 and 2024 datasets into a single master DataFrame (df).

Duplicate Removal: Checks for and removes duplicate rows based on track and artist combinations.

E. Outlier Analysis & Export
Outlier Detection: The code uses the IQR (Interquartile Range) method to flag songs with unusually high or low performance (specifically in spotify_playlist and shazam_charts columns).

Saving: The cleaned and processed data is exported to a new file named spotify_cleaned.csv.

F. Exploratory Data Analysis (EDA)
The final section generates visualizations to understand data distribution:

Histogram: To observe the distribution of streams (checking for skewness).

Boxplot: To visually identify outliers in playlist counts and streams.

Barplot: To rank top artists by track count or total streams.
