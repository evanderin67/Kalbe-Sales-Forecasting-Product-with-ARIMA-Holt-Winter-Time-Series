# Sales Forecasting Kalbe's Product with ARIMA & Holt Winter Time Series

This project aims to built *sales forecast* webapps for Category A, Category B, Product A1, Product A2, Product B1 & Product B2

# File Explanation on Github

This repository consists of several files, namely :

- Folder `deployment` = Contains files used for *deployment* to `HuggingFace` (contains models, python applications etc.)
- `kalbe_ftds_rmt17_evan_derin_ihsanudin.ipynb` = This file is the main *notebook* used to explore dataset and built model
- `inferencing_kalbe_ftds_rmt17_evan_derin_ihsanudin.ipynb`= *Notebook* used for *testing inference*. Inferencing is done on a separate *notebook* to prove that the model can run on a *notebook* that is *clean* of variables
- `url.txt` = Deployment URL to HuggingFace

# Brief Summary of Project

The flow of this *project*, First EDA (*Exploratory Data Analysis*) to find out the basic picture of the *dataset*. Second, *cleaning* and *preprocessing* of the *dataset*. Third, I did *modeling* with the following details:

- Kategori A : ARIMA (`MAE` 3.69)
- Kategori B : ARIMA (`MAE` 194.48)
- Produk A1 : ARIMA (`MAE` 7.4)
- Produk A2 : ARIMA (`MAE` 1.73)
- Produk B1 : Holt Winter (`MAE` 120.9)
- Produk B2 : Holt Winter (`MAE` 118.66)

# Project Conclusion


1. Forecast Model for Sales Category A  

    - Model can define trend and seasonality in the dataset
    - Model has MAE +- 3.69. **This error is small because, *range* sales in category A is 1,100-1,767**
    - Model tends to predict sales higher than the actual value

2. Forecast Model for Sales Category B

    - Model can define trend and seasonality in the dataset
    - Model has MAE +- 194.48. **This error is small because, *range* sales in category B is 970-6,435**.
    - Model tends to predict sales higher than the actual value

3. Forecast Model for Sales Product A1

    - Model can define trend and seasonality in the dataset 
    - Model has MAE +- 7.4. **This error is small because, *range* sales in product A1 is 100-210**
    - Model tends to predict sales higher than the actual value

4. Forecast Model for Sales Product A2

    - Model can define trend and seasonality in the dataset
    - Model has MAE +- 1.73. **This error is small because, *range* sales in product A2 is 1,000-1,558**
    - Model tends to predict sales lower than the actual value

5. Forecast Model for Sales Product B1

    - Model can define seasonality of the dataset but cannot capture the trend
    - Model has MAE +- 120.9. **This error is small because, *range* sales in product B1 is 970-1,734**
    - Model tends to predict sales higher than the actual value


6. Forecast Model for Sales Product B2

    - Model can define seasonality of the dataset but cannot capture the trend
    - Model has MAE +- 118.66. **This error is small because, *range* sales in product B2 is 10-4,980**
    - Model tends to predict sales higher than the actual value

