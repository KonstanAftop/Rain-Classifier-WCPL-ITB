Rainfall Intensity Estimation from Spatial Rainfall Maps

Overview

This project automates the process of extracting and classifying rainfall intensity from spatial rainfall maps using OpenCV. The script downloads a rainfall map, extracts color data at a specific coordinate, and classifies the rainfall intensity based on predefined color mappings. The results are saved in a CSV file for further analysis.

Features

Automated data collection: Downloads spatial rainfall maps from a given URL.

Pixel-based classification: Extracts pixel color values from a predefined coordinate.

Rainfall classification based on BMKG thresholds:

No Rain: 0 mm

Low Rainfall: 0 - 5 mm

Medium Rainfall: 5 - 10 mm

High Rainfall: >10 mm

Data storage: Saves extracted data in a CSV file.

Automated execution: Runs daily at 10 UTC.

Daily forecast updates: Automatically adds the next day's rainfall prediction to the CSV file.

Algorithm Explanation

Date and Time Processing

Calculates the next day's date and formats it as YYYYMMDD.

Iterates over predefined time values (1, 4, 7, ..., 22) to fetch rainfall maps.

Image Scraping

Constructs a URL to download the rainfall map for the given date and time.

Uses img_scraper to download and save the image as hasil.png.

Color Classification

Loads hasil.png using OpenCV (cv2.imread).

Extracts the RGB values of the pixel at coordinates (333, 247).

Compares extracted RGB values against predefined BMKG thresholds:

No Rain: 0 mm

Low Rainfall: 0 - 5 mm

Medium Rainfall: 5 - 10 mm

High Rainfall: >10 mm

Data Logging

Determines the rainfall category based on the extracted pixel color.

Stores the date, time, and rainfall category as a row in hasil.csv.

Output Format

The script generates a hasil.csv file with the following structure:

Date, Time, No Rain, Low, Medium, High
20250228, 1, 0, 1, 0, 0
20250228, 4, 0, 0, 1, 0
...

Future Improvements

Process multiple points in the image for a spatial analysis of rainfall.

Enhance the algorithm with machine learning for better color classification.

Author

Konstan Aftop Anewata Ndruru - GitHub Profile

