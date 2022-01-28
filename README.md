[![Continuous Integration](https://github.com/OpenSourceEconomics/ose-scientific-computing-course-space_farers/actions/workflows/ci.yml/badge.svg)](https://github.com/OpenSourceEconomics/ose-data-science-course-project-Abraham-newbie/actions/workflows/ci.yml) [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ose-scientific-computing-course-space_farers/master?filepath=project_notebook.ipynb)
[![nbviewer](https://raw.githubusercontent.com/jupyter/design/master/logos/Badges/nbviewer_badge.svg)](https://nbviewer.jupyter.org/github/OpenSourceEconomics/ose-scientific-computing-course-space_farers/blob/master/project_notebook.ipynb)



# Prediction of Crime Rates using Brightness derived from Nighttime Satellite Light Images - VIIRS

---
OSE Scientific Computing | Winter 2021, M.Sc. in Economics, University of Bonn | [Sona Verdiyeva](https://github.com/s6soverd) and [Abraham Raju](https://github.com/Abraham-newbie)
---

This notebook contains derivation of brightness index from [VIIRS Nighttime Satellite Light Images](https://developers.google.com/earth-engine/datasets/catalog/NOAA_VIIRS_DNB_MONTHLY_V1_VCMSLCFG), and with the addition of other control variables, the prediction of crime rates in the city of Portland, Oregano state in US. As far as the brightness index concerns, the index is derived for all the neighborhoods in the city of Portland, for which the 'offense type and occurrence' datasets are available. 


## Overview of the Project:

Spatial Analysis of crime is the use of Geospatial Information to visualize the spatial data for explanatory statistical analysis and as well as with the purpose of identifying how certain factors (e.g, population characteristics, structural or ecological changes etc.) affect the spatial patterns of crime.  Crime mapping, hence, can be used for resource allocation and policy improvement purposes, so that the police force has a more centralized knowledge of the hotspots of different crime types across time and space and the concerns of the local populace are better addressed. <br>
This project focuses on the addition of brightness values derived from Nighttime Satellite Image Collection in predicting the number of crime occurrences that are more bound to happen during the night, and see whether the lights do hold a predictive power over crime occurrence or not. <br>
The structure of the notebook is as follows. The first section explains the VIIRS - Nighttime Satellite Light Images, followed by how the brightness values across time given an area of interest is derived. All the functions are placed in their corresponding files in auxiliary folder. Since Continuous Integration was failing in installing neccessary packages (geopandas, geemap, ee, os, folium, fiona), the certain functions are commented out; however, their outputs are saved. <br>
To run this notebook with uncommented functions, one could create a local environment by running the below commands in the command line of shell:
```python
! conda create --name geo
! conda activate geo
! conda install mamba –c conda –forge     #Instaling mamba, that makes the installation of ‘geemap’ package faster
! mamba install geemap –c conda –forge
! conda install –c anaconda ipykernel
! conda config --prepend channels conda-forge
! conda create -n geo --strict-channel-priority geopandas jupyterlab  #Installing geopandas on Windows
! python –m ipykernel install --user --name = geo   #This sets this conda environment on your jupyter notebook
```
The follow-up subsection displays an example derivation for a given latitude-longitude point, the output of which is plotted against time. The unit test is written for testing couple of features of the brightness function. <br>
In the subsequent section, the data is prepared for the further analysis, by concatenating the crime datasets across years and matching the names of neighborhoods inside crime dataset with those in brightness index dataframe. Since brightness index dataframe is based on a shapefile of neighborhoods and their corresponding geometry information and crime datasets are sourced from a different website, there were differences in how the names of the same neighborhood was written. After the names were matched, the datasets were merged and saved into three different files, whether the crime occurred during the daytime, or nighttime, or all day long. <br>
The interactive mapping section explores the geospatial analysis of crime patterns against the distribution of brightness and population by neighborhoods in Portland. <br>
The section on Random Forest Regression explores the predictive power of brightness values in predicting the crime occurrence number, and compares the accuracy metric of the model against that of the rudimentary baseline model.



## References:

1. The World Bank. [Open Night Lights](https://github.com/worldbank/OpenNightLights): Collection of tools and training materials for exploring the open Nighttime Lights repository. <br>
2. Hitesh Kumar Reddy ToppiReddy, Bhavna Saini, Ginika Mahajan. (2018). Crime Prediction & Monitoring Framework Based on Spatial Analysis. *Procedia Computer Science*, 132, 696-705. <br>
3. Hongjian Wang, Daniel Kifer, Corina Graif, Zhenhui Li. (2016). Crime Rate Inference with Big Data. *KDD '16: Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining*,  635–644. <br>
4. Kadziolka Kinga. (2016). Analysis of the Crime rate in Poland in Spatial and Temporal Terms. *Central and Eastern European Journal of Management and Economics (CEEJME)*, 1, 81-96. <br>
5. Saffet Erdogan, Mustafa Yalcin, Mehmet Ali Dereli. (2013). Exploratory spatial analysis of crimes against property in Turkey. *Crime Law and Social Change*, 59, 63–78. <br>
6. Xi Chen, William D. Nordhaus. (2019). VIIRS Nighttime Lights in the Estimation of Cross-Sectional and Time-Series GDP. *Remote Sensing*, 1-11. <br>
7. Feng-Chi Hsu, Kimberly E. Baugh, Tilottama Ghosh, Mikhail Zhizhin, Christopher D. Elvidge. (2015). DMSP-OLS Radiance Calibrated Nighttime Lights Time Series with Intercalibration. *Remote Sensing*, 2, 1855-1876.


---
<a href="https://nbviewer.jupyter.org/github/OpenSourceEconomics/ose-scientific-computing-course-space_farers/blob/master/project_sv_environment.ipynb"
   target="_parent">
   <img align="center"
  src="https://raw.githubusercontent.com/jupyter/design/master/logos/Badges/nbviewer_badge.png"
      width="109" height="20">
</a>
<a href="https://mybinder.org/v2/gh/OpenSourceEconomics/ose-scientific-computing-course-space_farers/master?filepath=project_sv_environment.ipynb"
    target="_parent">
    <img align="center"
       src="https://mybinder.org/badge_logo.svg"
       width="109" height="20">
</a>


![Continuous Integration](https://github.com/OpenSourceEconomics/ose-scientific-computing-course-space_farers/workflows/Continuous%20Integration/badge.svg)

---





