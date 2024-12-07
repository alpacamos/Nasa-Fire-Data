# Brightness Temperature of Fire across the United States

## Project Overview

This project analyzes near real-time (NRT) active fire data collected by NASA's Moderate Resolution Image Spectroradiometer (MODIS) sensors on the Aqua and Terra satellites. The study focuses on the brightness temperature of fires in the contiguous United States during August 2023, exploring spatial-temporal characteristics using statistical methods.

## Data Description

The dataset, **modis_2023_United_States**, includes 14 variables, such as latitude, longitude, brightness temperature (Kelvin), pixel dimensions, satellite type, confidence levels, fire radiative power (FRP), and time of day. After preprocessing, the dataset was filtered to include brightness values ≤ 350 K, focusing on the first 8 days of August for detailed analysis.

## Objectives

- Analyze the spatial-temporal variability of fire brightness.
- Apply interpolation techniques to predict fire intensity at unobserved locations.
- Compare the performance of Inverse Distance Weighting (IDW) and Gaussian kernel interpolation.

## Methodology

### Interpolation Techniques
1. **IDW Interpolation**: Estimates unknown values using a weighted average of nearby points, with closer points assigned higher weights.
2. **Gaussian Kernel Interpolation**: Applies a Gaussian function to enhance the influence of nearby points, smoothing predictions.

### Model Evaluation
- Leave-One-Out Cross-Validation (LOOCV) was used to evaluate model performance, minimizing Mean Squared Error (MSE).
- Parameters for IDW (\(\alpha\)) and Gaussian kernel (\(\theta\)) were optimized to achieve the best predictive accuracy.

## Results

- **IDW**: Optimal (alpha = 1.075), RMSE = 9.05 K (2.59% of the brightness range).
- **Gaussian Kernel**: Optimal (theta = 1.465), RMSE = 8.72 K (2.49% of the brightness range).
- Gaussian kernel slightly outperformed IDW, offering lower prediction errors and better accuracy for spatial-temporal modeling.

## Key Insights

- Fire intensity is higher in the Southwest, likely due to desert climates.
- Eastern states experience lower-intensity fires, while mountainous regions in the North show minimal fire activity within the analyzed range.
- Spatial-temporal modeling highlighted the importance of incorporating both spatial and temporal dimensions in fire analysis.

## Limitations

- Exclusion of brightness values > 350 K limited the scope of conclusions.
- Analysis focused on a single week in August, potentially missing seasonal variations.
- Hawaii and Alaska were not included, restricting the study to the contiguous U.S.

## Conclusion

This project demonstrates the utility of spatial-temporal modeling in understanding fire behavior, with Gaussian kernel interpolation providing a more accurate prediction framework compared to IDW. The insights gained emphasize the role of geographic and climatic factors in fire intensity across the United States. 

