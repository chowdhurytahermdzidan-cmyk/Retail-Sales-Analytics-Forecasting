# Reproduction guide

The repo includes the **three original CSV datasets** in `01_Raw_Data/` (Kaggle dataset licensed CC0) and the original Power BI dashboard in `powerbi/`.

## Python notebooks

1. Download the repository using **Code → Download ZIP** and extract it, or clone it with Git.
2. Open a terminal inside the `Retail-Sales-Analytics-Forecasting` project folder (the folder containing `requirements.txt`).
3. Create a Python environment if desired, then install dependencies with `pip install -r requirements.txt`.
4. Start Jupyter from the project root with `jupyter lab` (or open the notebooks in VS Code).
5. Run `notebooks/01_data_preparation_and_eda.ipynb` first. It reads the three source CSVs and creates the merged dataset at `02_Cleaned_Data/retail_analysis_data.csv`.
6. Run `notebooks/02_sales_forecasting_and_holiday_analysis.ipynb` second. Model training and evaluation can take several minutes.
7. Compare notebook output to the precomputed tables in `results/` and the charts in `figures/`.

## Power BI report

Open `powerbi/Retail_Sales_EDA_Dashboard.pbix` in Microsoft Power BI Desktop (Windows). It is a downloadable interactive dashboard, not a public web app. If Power BI reports a broken CSV file path, open **Transform data → Data source settings**, choose the relevant source and point it to the matching CSV file in `01_Raw_Data/`, then refresh.

## What is reproducible?

The notebooks and source CSVs are available for rerunning the analysis. The saved forecasting evaluation statistics are drawn from the earlier executed project outputs; compare them against a new local run rather than assuming every environment yields byte-identical results. The final nine-week forecasts extend beyond the recorded data and remain **unverified future predictions**.

Source and licence: [Kaggle Retail Data Analytics](https://www.kaggle.com/datasets/manjeetsingh/retaildataset/data), CC0 (licence as displayed on 8 October 2026).
