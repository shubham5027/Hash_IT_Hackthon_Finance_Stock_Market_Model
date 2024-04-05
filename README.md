# Stock Price Analysis and Prediction Responsive Webapp using Machine Learning

Welcome to the Stock Price Prediction App! This app allows you to visualize stock price data, explore technical indicators, and make short-term price predictions using machine learning models.

URL For APP Deploy on Stramlit Cloud : https://faeznxii65hcfydtfkwnwk.streamlit.app/

## Table of Contents

- [Description](#description)
- [Features](#features)
- [Setup](#setup)
- [Usage](#usage)
- [Technologies](#technologies)
- [License](#license)

## Description

The Stock Price Prediction App is a Streamlit-based web application that provides users with tools to analyze historical stock price data, visualize technical indicators, and make short-term price predictions using different machine learning models.

## Features

- **Visualize Technical Indicators**: Explore various technical indicators such as Bollinger Bands, MACD, RSI, SMA, and EMA to gain insights into stock price trends.

- **Recent Data Display**: View the most recent data of the selected stock, including the last 10 data points.

- **Price Prediction**: Predict future stock prices using machine learning models including Linear Regression, Random Forest Regressor, Extra Trees Regressor, KNeighbors Regressor, and XGBoost Regressor.

## Setup

1. Clone the repository:
   ```sh
   git clone https://github.com/shubham5027/Hash_IT_Hackthon.git
   ``

2. Install the required Python packages using pip:
   ```sh
   pip install -r requirements.txt
   ```

## Usage

3. Run the Streamlit app:
   ```sh
   streamlit run app.py
   ```

2. The app will open in your default web browser. Use the sidebar to choose options for visualization, recent data display, or making price predictions.

3. Follow the on-screen instructions to input the stock symbol, select a date range, and choose technical indicators or prediction models.

## Technologies

- Python
- Streamlit
- pandas
- yfinance
- ta (Technical Analysis Library)
- scikit-learn
- XGBoost

  URL For APP Deploy on Stramlit Cloud : https://faeznxii65hcfydtfkwnwk.streamlit.app/

- ![Screenshot 2024-03-31 163716](https://github.com/shubham5027/Hash_IT_Hackthon/assets/132193443/ad521cac-00c9-4335-a6cc-058d68be23fd)
`![Screenshot 2024-03-31 155726](https://github.com/shubham5027/Hash_IT_Hackthon/assets/132193443/5459fd7d-5534-4cd2-8909-eb081a8289d1)
![Screenshot 2024-03-31 155704](https://github.com/shubham5027/Hash_IT_Hackthon/assets/132193443/20c2132d-c897-455c-8548-11ba1c479cb3)



[hash_it_hack.webm](https://github.com/shubham5027/Hash_IT_Hackthon/assets/132193443/e78a82d2-6dd8-4d49-aecf-179f266072b9)

## Deploy to Docker 

1. Navigate to the directory where your Dockerfile exists.

2. Build the docker image using the command -
     docker build -t <image-name> .
     -t = tag

3. Run the image once the build is finished with the following command -
   docker run -d -p 8501:8501 <image-name>
      -d = detached mode
      -p = port mapping <local host >:<container host>

      URL for APP deploy on docker : https://drive.google.com/file/d/1uEdPxrN7HikjR5XxN0u_6jOOfBLX90KC/view?usp=sharing