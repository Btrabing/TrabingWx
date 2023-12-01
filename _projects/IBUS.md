---
layout: page
title: Intensity Bias and Uncertainty Scheme (IBUS)
description: IBUS Reduces Bias and Provides Uncertainty to Intensity Forecasts 
img: assets/img/DSHP_LGEM_IC_24_2020.png
importance: 3
category: Forecasting
giscus_comments: true
---

Statistical models are important for forecasting tropical cyclone intensity even though we know it has biases. Almost all statistical models suffer when forecasting extreme values. So I tried to apply a bias correction for that by calculating the biases when different intensity change thresholds are applied. This work is published in Weather and Forecasting and you can find the reference below.

<h3>Creating the Bias Correction </h3>
The bias correction was created using DSHP and LGEM intensity change forecasts between 2010-2019. We condition the forecasts on a range of values, such as 13-17 kt which would translate to a 15 kt forecast by NHC, and then examine the distribution of those forecasts. We calculate the standard deviation and bias of the forecast distributions at each time period and for a spectrum of intensity change values. The figure above shows an example of the binned distribution of intensity changes conditioned on the forecast for DSHP and LGEM. In addition to the bias, we get a measure of the uncertainty of the forecast using the standard deviation. The mean intensity change can be subtracted from the forecast to remove the intensity forecast bias. Using this method to create a bias correction means that we are using past performance to improve future forecasts and requires a large sample size of past forecasts.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/DSHP_LGEM_IC_24_2020.png" title="Distributions of DSHP and LGEM errors given forecast" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison between the DSHP and LGEM distribution of intensity change forecast errors given the intensity change forecast.
</div>


A bias correction using previous forecasts is inherently limited by previous events, as in we cannot bias correct a forecasted value that has not been predicted in the past. Sample size also becomes an issue for rare forecasts, such as the top few percentiles of the intensity change distribution. In order to account for extreme forecasts, we bin the top and bottom 3rd percentiles and apply it to any intensity change that exceeds those percentiles. For example, DSHP has never forecasted a 50 kt intensification in 24 h but should it occur, we assume that the bias would be similar to a 30 kt intensification which is in the 97th percentile. To help with bins that may have an under representative sample of values and to reduce noise, we apply a 2D Gaussian filter to the bias correction field. 


<h3> Evaluating the Bias Correction </h3>
We evaluate the bias correction using a leave one year out methodology. One year is removed from the dataset which is used to calculate the bias correction, and then the bias correction is tested on that year. This allows us to assess both the sensitivity of the bias correction to individual years and also to test the viability of the bias correction. Overall the bias correction has a small effect on short time scales, with some mixed results depending on the year. At long time scales the bias correction has a larger impact and is overall positive. It should be noted that large negative skill for some years can be more attributed to the missing large intensity change events. For example, 2017 is the only year in the dataset that had a -55 kt in 132 h forecast (and there were two), which caused large errors when excluded. The figure below shows the skill of the bias corrected DSHP and LGEM models relative to the previous version for both the Atlantic and East Pacific basins. Each dot is the skill for a year of evaluation.     
  

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Leave_one_out_verif_skill.png" title="Leave-on-out verification of DSHP and LGEM" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison between the DSHP and LGEM performance of bias correction in the Atlantic and East Pacific basins using a leave-one-year out verification.
</div>




---

Trabing, B. C., K. D. Musgrave, M. DeMaria, and E. Blake, 2022: A simple bias and uncertainty scheme for tropical cyclone intensity change forecasts. Wea. Forecasting, 37, 1957–1972, https://doi.org/10.1175/WAF-D-22-0074.1.

