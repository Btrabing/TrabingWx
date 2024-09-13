---
layout: page
title: Radiative Transfer
description: Radiative Impacts on Tropical Cyclones
img: assets/img/SDM_SumTCvMaxSW_Days2345_2h.png
importance: 1
category: Research
---


During my M.S. and Ph.D. I examined how radiation, specifically shortwave radiation, impacted tropical cyclone structure and intensity. Some of this work I never published but can still be found in my dissertaion. 


One of the biggest concerns I had was with the representation of the radiation schemes with cloud microphysics schemes in numerical weather prediction models. I compared different radiation schemes in a simple single domain model shown below using the same microphysics schemes and they produce different answers based on the interactions and assumptions made. It is important when running WRF or other research models to understand the limitations of the schemes, but a comprehensive study showing the feedbacks of these schemes hasn't been conducted yet. If only I had the time and the resources to finish out the project. 

Below is a comparison of the relationship between the column integrated total condensate and the maximum heating rate in that column for a bunch of different radiation schemes with the same microphysics scheme. The relationship between these variables is significantly different between the radiation schemes with the CAM radiation model never producing heating rates above .5 K/h compared to the 2 K/h in the other models. The distribution shapes also vary with some having a spike in heating rates at low condensate values caused by a thick upper-level cloud.  


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/SDM_SumTCvMaxSW_Days2345_2h.png" title="Radiative Heating Tendencies from WRF" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Comparison between the radiative tendencies computed in a single domain WRF run for different radiation schemes.
</div>



If you are interested in learning more about radiative transfer, I found that one of the easiest tools to use is the Santa Barbara DISORT Atmospheric Radiative Transfer (SBDART) model. The embedded acronymn DISORT stands for discrete ordinates radiative transfer. It is free to download and use and I would recommend checking out the documentation referenced below. I have a handy notebook that I wrote while TAing radiative transfer at CSU using python. You can read and plot the output from SBDART examples with the code you can find <a href="../../assets/RP_SBDART_ATS622.html">here</a>.


---


Ricchiazzi, P., S. Yang, C. Gautier, and D. Sowle, 1998: SBDART: A Research and Teaching Software Tool for Plane-Parallel Radiative Transfer in the Earth's Atmosphere. Bull. Amer. Meteor. Soc., 79, 2101–2114, https://doi.org/10.1175/1520-0477(1998)079<2101:SARATS>2.0.CO;2. 






