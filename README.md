# ClimateScope — Interactive Climate Trend Dashboard

**Static GitHub Pages application.** No backend, Python server, database, or IoT device is required.

## What it does
- Fetches real daily historical reanalysis data from the Open-Meteo Historical Weather API (ERA5/ERA5-Land options through the API).
- Fetches daily downscaled climate-model series from the Open-Meteo Climate API (CMIP6-related high-resolution models).
- Interactive controls for coordinates, time period, climate variable, aggregation, hot-day threshold, anomaly baseline, and climate models.
- Annual trends, baseline-relative anomalies, heat-extreme counts when daily maximum temperature is available, seasonal profile, model-specific series and a multi-model mean.
- Annual CSV export; no uploaded file is sent to a server.

## Deploy
1. Create a public GitHub repository named `ClimateScope`.
2. Upload `index.html` and `README.md` to the root of the `main` branch.
3. Go to **Settings → Pages**.
4. Under Build and deployment, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, and Save.
5. Open the published GitHub Pages URL after the deployment completes.

## Data sources
- Historical Weather API: https://open-meteo.com/en/docs/historical-weather-api
- Climate Change API: https://open-meteo.com/en/docs/climate-api
- API terms: https://open-meteo.com/en/features#terms

The application requests data directly from the user's browser. Internet access, API availability, browser network policy and provider limits may affect requests. Climate model mode may require smaller date ranges or fewer models if the API request is large.

## Scientific limitations
- Historical weather products are reanalysis, not necessarily station observations. Use a consistent reanalysis product for trend analysis.
- Climate API data are climate-model simulations and should not be labelled as observed values, even for the historical period.
- The available high-resolution climate-model data described by the provider cover 1950–2050. Do not extrapolate beyond the documented range or imply these are official projections for every emissions pathway.
- OLS trend is descriptive. It does not automatically account for serial correlation, changepoints, nonlinearity, missingness or measurement uncertainty.
- Heat-day count uses daily maximum temperature above the user-set threshold. Ensure the selected variable and data source support this calculation before interpretation.
- For publication, document the dataset/model version, baseline, units, missing data, temporal aggregation, validation and uncertainty.

## Technology
HTML, CSS, vanilla JavaScript, Chart.js from a CDN, Open-Meteo public APIs. All charts and calculations run in the browser.
