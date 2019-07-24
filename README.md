# Deforestation Rate Chart (Browser-Side)

## Description and Purpose

The *Deforestation Rate Chart* is used both at the national level and jurisdictional level to visually represent annual deforestation-rate data for the region being displayed.

### National Deforestation Rate

At the national level, only the deforestation rate is displayed.

### Additional Overlays For Jurisdictions

At the jurisdictional level, several additional data overlays are combined to present a visualization of how the underlying series compares over time with established reference rates as well as a future target rate. Briefly, the overlays are:

- **Rio Branco Declaration Deforestation Reduction Goal** (single point)
- **Deforestation Reference Rate** (single point or line) If a single year is specified, a point is displayed. If a year range is specified, a line segment over the range is displayed.
- **Historical Reference Rates** (optional) (multiple line segments displayed as steps) Jurisdictions may specify reference rates defined prior to the establishment of the currently accepted *Deforestation Reference Rate*. These rates are displayed as steps appearing before *Deforestation Reference Rate* thus forming a complete chronological data series.
- **Regression Line** (single line) Regression line is drawn from the earliest established *Reference Rate* point to the *Rio Branco Declaration Deforestation Reduction Goal* point.

![Rate Chart](/public/images/screenshots/rate_chart.png)

## Technical Overview

This repository contains the browser-side code for the *Deforestation Rate* chart. The [Chart.js](https://www.chartjs.org/) library is used.

Note that chart data is passed server-side using HTML data attributes. See the website EJS partial [kdb-site/views/partials/deforestation-rate-chart.ejs](https://github.com/gcftaskforce/kdb-site/blob/master/views/partials/deforestation-rate-chart.ejs) for a complete understanding.

The full chart with all data overlays is displayed on both the "Overview" and "Forest Monitoring" tabs for **jurisdictional** content.

The simplified *national* version is displayed on the "Overview" tab for  **national** content.

Note the partial must be passed a `fieldName` argument specifying the (property) name of the "Deforestation Rate" (`national_deforestation_rate` or `deforestation_rates` for national or jurisdictional data respectively).

The table below summarizes the names of the underlying data properties.

Label | Data Property Name | Notes
----- | ------------- | -----
Deforestation Rates | `national_deforestation_rate` or `deforestation_rates` | `Array` kind edited by client via the CMS
Deforestation Reference Rate | `deforestationReferenceRate` | `Value` kind (with year or year range) edited by client via the CMS
Historical Reference Rates | `deforestationReferenceRates` | Javascript array defined on a per-jurisdiction basis in the API's 'etc/regions' (**not** edited by client via the CMS)

Note that the field **Historical Reference Rates** is not currently displayed on the website but it is part of the data passed by the API.
