---
layout: page
title: TC Modeling
description: Modeling with WRF
img: assets/img/WRF_Jebi_MT.gif 
importance: 3
category: Reseach
---


## Weather Research and Forecasting (WRF) Model

One way to help better understand our atmosphere is to model it using numerical weather prediction models. <a href="https://www.mmm.ucar.edu/models/wrf"> WRF</a> is a great tool with a lot of detailed documentation that makes it valuable to the atmospheric community. 

## Using WRF

WRF is free to use and is in active development by the community. I wrote some code to help read in and plot the output. If you are new to WRF and need help understanding the output structure take a look at <a href="../../assets/Read_WRF.html"> this jupyter notebook.</a> If you have questions feel free to reach out.


## Idealized Study

WRF can be used in an idealized framework to help better understand the physical processes we are interested in in a simplistic framework. WRF ideal can be configured in a number of ways, but I configured it to simulate tropical cyclones in a vortex following framework. I conducted several experiments with idealized WRF to examine how radiation, upper-tropospheric temperatures, and tropical cyclone intensity are related. I also took a look at tropical cyclone structure and analyzed why some of the idealized simulations had secondary eyewalls form.



## Validation Study

The goal of numerical weather prediction models is to provide a reasonable forecast of the future state of the atmosphere. We also need to ensure that the models future state is reasonable by conducting validation and verification studies. 

The last part of my dissertation included a validation study of how radiation and microphysics schemes interact to influence the precipation structure of tropical cyclones. Single moment and double moment microphysics schemes have bigger differences in precipation structure when interactive radiation is included. In particular, double moment schemes are able to produce significantly larger amounts of stratiform precipiation that may be more realistic.   


