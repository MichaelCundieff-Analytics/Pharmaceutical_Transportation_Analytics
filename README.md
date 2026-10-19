# Pharmaceutical Transportation & Supply Chain Analytics

Independent Python portfolio project by Michael Cundieff. The project demonstrates data integrity
verification, transportation KPI development, interactive visualization, and practical business reasoning.
It uses historical pharmaceutical supply chain data to support interview discussion.

## Dataset and tools

- Source: [USAID Supply Chain Shipment Pricing Data on Kaggle](https://www.kaggle.com/datasets/apoorvwatsky/supply-chain-shipment-pricing-data).
- Exact downloaded file: `SCMS_Delivery_History_Dataset_20150929.csv`; retrieved October 14, 2026.
- 10,324 product lines, 33 original fields, and 7,030 validated `ASN/DN #` delivery groups.
- Actual delivery dates: May 2006–September 2015. USAID attribution is retained; these are not Cencora records.
- Python 3.12, Pandas, Plotly Express, and Jupyter. No machine learning or forecasting.

## Analysis and findings

Eight interactive charts examine mode mix, overall on-time delivery, reliability by mode and destination,
recorded freight by mode, freight-cost quartiles versus reliability, cost distribution, and annual performance.

- On-time delivery: **88.6%** (6,222/7,020 eligible groups).
- Observed late rate: **20.6% truck** versus **8.5% air**. Route and cargo mix differ.
- The **310 groups in the upper 5% of numeric freight amounts account for 28.0%**
  of the recorded numeric subtotal.
- Numeric freight coverage is **88.2%**. The subtotal is incomplete transportation spend.

Each delivery identifier has exactly one first-line record. Shared cost references are checked and are
not summed again. Ten groups with conflicting schedules are excluded only from delivery performance.
Missing costs are not zero-filled, and unusual observations are retained. The source does not support
precise product-level/country-level shipping-rate or transit-lead-time claims. Observed differences are
not causal effects, and no savings or operating improvements are claimed.

## Files

| File | Purpose |
| --- | --- |
| `Pharmaceutical_Transportation_Analytics.ipynb` | Complete notebook with executed code and saved outputs |
| `Interactive_Project_Report.html` | Standalone interactive report; open directly in a browser |
| `cleaned_transportation_data.csv` | Product lines plus parsed fields, quality flags, and delivery-group status |
| `delivery_summary.csv` | One record per delivery group; direct chart-analysis population |
| `data/SCMS_Delivery_History_Dataset_20150929.csv` | Unmodified original CSV, read with `cp1252` encoding |
| `Interview_Talking_Points.md` | A short project explanation, three findings, and five question/answer pairs |
| `Resume_Bullets.md` | Two quantified, defensible project bullets |
| `requirements.txt` | Project dependencies |

## Run

Unzip the project, open a terminal inside its folder, and use Python 3.10 or later (tested on 3.12).

```bash
python -m pip install -r requirements.txt
jupyter notebook Pharmaceutical_Transportation_Analytics.ipynb
```

Trust the notebook if prompted, then choose **Restart Kernel and Run All Cells**. All preparation,
calculations, eight charts, interpretations, and exports are in this single notebook. CSV outputs are
written to the project folder. The saved report provides an immediate chart view without Python setup.

Optional command-line execution:

```bash
jupyter nbconvert --to notebook --execute --inplace Pharmaceutical_Transportation_Analytics.ipynb
```

All 30 code cells were executed sequentially through IPython with rich outputs captured. Data assertions
check identifier uniqueness, first-line ownership, reference links, group counts, KPI populations, and
freight reconciliation. Standard kernel startup in the build environment was unavailable, so execution
used the same IPython cell engine without a network kernel.
All eight Plotly figure specifications and embedded chart scripts were validated. Browser screenshot
review was unavailable in the build environment.

The original CSV's SHA-256 is `9cffdb4ab8c6135b0f999c91b3a5c6e88a3c3dfc28c7c85feb9e97f986e3578a`.
Kaggle identifies the dataset license as “Data files © Original Authors”; this project does not assign
a new license to the source data.
