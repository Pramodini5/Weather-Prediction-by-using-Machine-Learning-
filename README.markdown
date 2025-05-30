# Weather Data Prediction Using Machine Learning

## Project Overview
This project develops a weather prediction system using machine learning techniques to forecast key weather attributes such as maximum temperature. The system leverages historical weather data from the National Centers for Environmental Information (NCDC) at NOAA, employing data preprocessing, feature engineering, and a Ridge regression model to achieve accurate predictions.

## Dataset
The dataset is sourced from the [NCDC NOAA](https://www.ncdc.noaa.gov/cdo-web/search) and includes historical weather data with attributes like:
- Maximum and minimum temperature
- Precipitation
- Humidity
- Wind speed
- Atmospheric pressure

The dataset spans several years and is preprocessed to handle missing values, normalize data, and convert dates into a `DatetimeIndex` for time-series analysis.

## Prerequisites
To run this project, ensure you have the following:
- **Python Libraries**:
  - `pandas` for data manipulation
  - `scikit-learn` for machine learning models
  - `matplotlib` for data visualization
- **Environment**: Google Colab or Jupyter Notebook
- **Dataset**: Access to the NOAA weather dataset or a similar dataset (e.g., `local_weather.csv`)

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/your-repository.git
   ```
2. Install required Python libraries:
   ```bash
   pip install pandas scikit-learn matplotlib
   ```
3. Download the dataset from [NCDC NOAA](https://www.ncdc.noaa.gov/cdo-web/search) or use the provided `local_weather.csv`.

## Project Structure
- `local_weather.csv`: The input dataset (replace with your dataset from NOAA).
- `weather_prediction.ipynb`: The Jupyter Notebook containing the code for data preprocessing, feature engineering, model training, and evaluation.
- `README.md`: This file, providing an overview and instructions for the project.

## Usage
1. Open the Jupyter Notebook in Google Colab using the following link:
   [Google Colab Notebook](https://colab.research.google.com/drive/1bZAFq1JYN9ByBVuBXfgoZFm94B-SRheT)
2. Upload the dataset (`local_weather.csv`) to your Colab environment or modify the notebook to load the dataset from a URL.
3. Run the notebook cells sequentially to:
   - Load and preprocess the data
   - Perform feature engineering
   - Train and evaluate the Ridge regression model
   - Visualize the results

## Methodology
1. **Data Preprocessing**:
   - Missing precipitation values are filled with zeros.
   - Missing continuous data (e.g., temperature) is handled using forward-fill.
   - The date column is converted to a `DatetimeIndex`.
   - Irrelevant columns (e.g., snow, snow_depth) are dropped.
   - Continuous features are normalized for uniform scaling.

2. **Feature Engineering**:
   - `month_max`: Rolling average of monthly maximum temperatures.
   - `month_day_max`: Ratio of monthly to daily maximum temperature.
   - `max_min`: Ratio of maximum to minimum temperatures for diurnal variations.

3. **Model Training**:
   - A Ridge regression model is used to handle multicollinearity and prevent overfitting.
   - The dataset is split into training (1960–2020) and testing (2021 onwards) subsets.
   - Predictors include precipitation, maximum, and minimum temperatures.
   - The model is evaluated using Mean Absolute Error (MAE), achieving a score of 3.36.

4. **Results**:
   - The model effectively predicts maximum temperatures with an MAE of 3.36.
   - Visualizations compare actual vs. predicted values, highlighting seasonal trends.
   - Limitations include challenges in predicting extreme weather events due to unmodeled factors.

## Results
The Ridge regression model achieved an MAE of 3.36 for maximum temperature predictions, indicating robust performance in capturing seasonal patterns. However, it struggles with sudden, extreme weather events. Future improvements could include advanced models (e.g., Random Forests) or real-time data integration.

## How to Contribute
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit (`git commit -m "Add feature"`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

## References
- Spiegel, M. R. (1981). *Theory and Problems of Advanced Calculus: SI (metric) edition*. McGraw-Hill.
- National Center for Environmental Information. [https://www.ncdc.noaa.gov/cdo-web/](https://www.ncdc.noaa.gov/cdo-web/)
- Pedregosa, F., et al. (2011). Scikit-learn: Machine Learning in Python. *Journal of Machine Learning Research*, 12, 2825–2830.

## Contact
For questions or feedback, contact Suvarna Pramodini Duggirala at `adagg020jagaar.tau.edu`.