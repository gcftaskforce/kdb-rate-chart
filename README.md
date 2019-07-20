# Browser-Side Code for Deforestation Rate Chart

This repository contains the browser-side code for the KDB website's *Deforestation Rate* chart. The [Chart.js](https://www.chartjs.org/) library is used.

Note that chart data is passed server-side using HTML attributes. See the website EJS partial [kdb-site/views/partials/deforestation-rate-chart.ejs](https://github.com/gcftaskforce/kdb-site/blob/master/views/partials/deforestation-rate-chart.ejs) for a complete understanding.

## Overview

![Rate Chart](/public/images/screenshots/rate_chart.png)

Displayed on both the "Overview" and "Forest Monitoring" tabs for **jurisdictional** content.

Also the simplified *national* version on the "Overview" tab for  **national** content. Do not display goals and targets or the associated regression and threshold lines.

---

deforestation_rates / national_deforestation_rate

Deforestation Rates

this field name is passed to the partial.

---

deforestationReferenceRate (both amount and year)

Deforestation Reference Rate

"Forest Monitoring" tab

---

deforestation_reduction_goal (both amount and year)

Rio Branco Declaration Deforestation Reduction Goal

"Forest Monitoring" tab

coordinates of the green asterisk.

---

deforestationReferenceRates

Defined on a a per jurisdiction basis.

[kdb-api/etc/regions](https://github.com/gcftaskforce/kdb-api/tree/master/etc/regions)

Optional

---

If `deforestationReferenceRates` array is specified, these rates are pre-pended to the deforestationReferenceRate value.

- stepwise

- beginning of Rio Branco Declaration Deforestation regression becomes the beginning.
