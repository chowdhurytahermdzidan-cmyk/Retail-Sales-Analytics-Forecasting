# Methodology, results, limitations and provenance

## Data preparation

- Sales: 421,570 store-department-week rows. Features: 8,190 store-week rows. Stores: 45 store rows.
- Parsed the original day-first dates, checked types and missing cells, flagged negative sales, reconciled joins on Store and Date, and added calendar and holiday fields.
- Missing markdowns exist in the historical features, so markdown-based comparisons require special care.

## EDA

- Historic sales total: $6,737,218,987.11 from 5 Feb 2010 to 26 Oct 2012 (143 weekly periods).
- Average holiday-week sales: $50,529,955.16 from 10 observed holiday weeks; other weeks: $46,856,537.11 from 133 weeks, approximately 7.84% higher. These are descriptive comparisons, not the measured causal effect of holidays.
- Highest company-wide weekly total: 24 Dec 2010, $80,931,415.60; Store 20 total $301.4m and Store 33 total $37.2m.
- Correlation of physical store size with cumulative store sales: approximately 0.846; association does not establish causation.

## Forecast comparison (values transcribed from source notebook outputs)

- Time-ordered holdout: 10 Aug–26 Oct 2012, 32,938 eligible store–department–week rows.
- Histogram Gradient Boosting regressor with lagged sales, rolling means and contextual features: MAE $1,294.90, RMSE $2,696.99, holiday-weighted MAE $1,344.84, WAPE 7.74%.
- Same-test-set 52-week seasonal-naive reference: MAE $1,778.68, RMSE $3,752.05, weighted MAE $1,811.82, WAPE 10.63%.
- *Different forecasting exercise*: A four-event historical-holiday comparison used a weighted seasonal/13-week-level formula against a seasonal naive baseline; holiday average error should not be conflated with per-store-department test MAE.

## Limitations

The dataset ends in October 2012; there are no observed targets for later forecasts. Holiday sample sizes are small; holiday/nonholiday differences and markdown effects are not proof of causation. The model uses historical lag values and is not evidence of reliable real-time stock-order planning. Costs, margins, returns and inventory levels are unavailable.

## Attribution

This portfolio repackages technical artifacts from coursework originally submitted in a **group assessment**. It does not claim sole authorship of that original group submission. AI assistance was used for comparison, scripting support and explanation; reported numerical results were generated in notebooks rather than accepted as standalone AI estimates. The repository excludes student identifiers and institutional paperwork.

Dataset source: [Kaggle Retail Data Analytics](https://www.kaggle.com/datasets/manjeetsingh/retaildataset). The original three CSVs are reproduced under the dataset listing’s **CC0: Public Domain** licence. See [source and licence notes](DATA_SOURCE_AND_LICENSE.md).
