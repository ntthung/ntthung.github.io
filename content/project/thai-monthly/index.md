---
author: | 
  Stefano Galelli, Chenxi Xu, and Brendan Buckley
date: "2022-08-01"
categories: ""
#- Tree Rings
#- Hydrology and water resources
draft: false
excerpt: This project aims to develop a novel mathematical framework to achieve **monthly streamflow reconstruction** from **annual tree-ring data**. 
layout: single-proj
links:
- icon: open-access
  icon_pack: ai
  name: paper 1
  #url: https://doi.org/10.1029/2020WR029394
  url: "/publication/nguyen2021"
- icon: open-access
  icon_pack: ai
  name: paper 2
  #url: https://doi.org/10.1029/2022GL100442
  url: "/publication/nguyen2022"
- icon: closed-access
  icon_pack: ai
  name: Commentary
  #url: https://doi.org/10.1061/(ASCE)WR.1943-5452.0001422
  url: "/publication/galelli2021"
- icon: github
  icon_pack: fab
  name: Data & code 1
  url: https://github.com/ntthung/multiproxy-mbr
- icon: github
  icon_pack: fab
  name: Data & code 2
  url: https://github.com/ntthung/chao-phraya-monthly
- icon: r-project
  icon_pack: fab
  name: package
  url: https://cran.r-project.org/package=mbr
- icon: door-open
  icon_pack: fas
  name: Data on NOAA
  url: https://www.ncei.noaa.gov/access/paleo-search/study/36835
subtitle: 
tags:
- Thailand
- tree rings
- stable oxygen isotope
- streamflow reconstruction
title: Multi-Proxy, Monthly Climate Reconstruction
---

## Motivations & Objectives

Tree rings, with annual resolution and precise dating, can provide temporally high-resolution proxy records of past climate. However, annually-resolved tree ring data still restrict how tree-ring-based paleoclimate reconstructions can be used in subsequent applications, where finer resolutions are desirable. For example, it is often difficult to compare annual climate reconstructions against historical events, because an event may have happened outside the target season of the reconstruction, or two opposite events (a flood and a drought) may be smoothed out by a reconstruction that targets the annual average (Wise, 2021). In addition, and specific to water resources, annual streamflow reconstructions have provided important insights into surface water availability, but cannot be used directly in water management models which require monthly, weekly, or even daily data (Galelli et al., 2021).

**How do we obtain subannual climate reconstructions from annual tree rings?** Earliest attempts used statistical methods to disaggregate each annual value to multiple subannual ones, assuming a fixed relationship between the two resolutions (Prairie et al., 2007, 2008; Saito et al., 2015; Sauchyn & Ilich, 2017). Later works incorporated multiple species and sites, leveraging the fact that different tree species have different seasonal sensitivities to the hydroclimate, and that there can be different time lags in hydrologic responses at various sites (Stagge et al., 2018; Stahle et al., 2020; Wise, 2021). A third approach uses intra-annual measurements of stable oxygen isotope ratios (δ<sup>18</sup>O) in tree ring cellulose to reconstruct intra-annual precipitation (Xu et al., 2016, 2021). This approach is promising, but the current methods are time-consuming and expensive.

**We seek to address simultaneously two challenges that were previously considered in isolation:**

* How do we combine multiple paleoclimate proxies that have different seasonal sensitivity?
* How do we preserve the annual mass balance? That is, we need to ensure that the sum of the monthly precipitations or streamflows is close to the annual figures.

Our case study is the Chao Phraya River Basin, Thailand.

A novel aspect of this work is to **incorporate δ<sup>18</sup>O together with ring width**, motivated by an earlier result (Xu et al., 2019) that δ<sup>18</sup>O correlates strongly with streamflow in the peak monsoon season, which has been a difficult season for reconstruction with ring width.

## Results & Implications

We develop a novel method called mass balance regression (MBR). It is published as an R package named `mbr`. We first tested this framework with a seasonal recosntruction (wet and dry seasons) of the Ping River streamflow. The framework works really well (Nguyen et al., 2021). We then expanded our application to a monthly reconstruction at all four major tributaries (Ping, Nan, Yom, and Wang) of the Chao Phraya (Nguyen et al., 2022). We also wrote a commentary 

Our framework can be reapplied and expanded in several ways. First, the mass balance formulation is applicable to other climate variables such as precipitation, and to other contexts where a penalty term in the regression equation is desirable. For example, if one wishes to reconstruct streamflow at two tributaries as well as the main stream of a river, the mass balance adjustment should be used to minimize the differences between the total flow of the tributaries and the flow on the main stream. Second, if more proxies—such as wood density (Schweingruber & Briffa, 1996) or blue intensity (Buckley et al., 2018)—are available, they can also be incorporated into the reconstruction framework.

Our results are particularly important when seen through the lens of water management. The Chao Phraya is water-stressed: freshwater availability per capita is about 2,230 m<sup>3</sup>/year, less than the national average (3,244 m<sup>3</sup>/year) and only 39% of the world's average (5,732 m3/year). Worse still, water availability is not constant throughout the year, as the monsoon brings stark contrasts to the annual hydrograph. Our monthly reconstruction could be used to operate the Chao Phraya water system better. For example, it could help coordinate the operations of Thailand's two largest reservoirs—Bhumibol and Sirikit—both of which are in the Chao Phraya, to mitigate concurrent floods or droughts while meeting irrigation and hydropower demands, which vary greatly from month to month. Our monthly-resolved reconstructions have partly bridged the gap between what tree rings offer and what water management needs.

## Products 

### Publications

**Nguyen, H. T. T.**<span style="color: darkorange">(*)</span>, Galelli, S., Xu, C., & Buckley, B. M. (2021). Multi‐Proxy, Multi‐Season Streamflow Reconstruction With Mass Balance Adjustment. Water Resources Research, 57(8). https://doi.org/10.1029/2020WR029394

**Nguyen, H. T. T.**<span style="color: darkorange">(*)</span>, Galelli, S., Xu, C., & Buckley, B. M. (2022). Droughts, Pluvials, and Wet Season Timing Across the Chao Phraya River Basin: A 254-Year Monthly Reconstruction From Tree Ring Widths and δ18O. Geophysical Research Letters, 49(17), e2022GL100442. https://doi.org/10.1029/2022GL100442

Galelli, S., **Nguyen, H. T. T.**, Turner, S. W. D., & Buckley, B. M. (2021). Time to Use Dendrohydrological Data in Water Resources Management? Journal of Water Resources Planning and Management, 147(8), 01821001. https://doi.org/10.1061/(ASCE)WR.1943-5452.0001422

### Data and code

R package [`mbr`](https://cran.r-project.org/package=mbr).

GitHub repos for the [seasonal](https://github.com/ntthung/multiproxy-mbr) and [monthly](https://github.com/ntthung/chao-phraya-monthly) reconstructions.

The monthly reconstructions are avaialble on the [NOAA Paleoclimate Database](https://www.ncei.noaa.gov/access/paleo-search/study/36835).

## References

Buckley, B. M., Hansen, K. G., Griffin, K. L., Schmiege, S., Oelkers, R., D’Arrigo, R. D., Stahle, D. K., Davi, N. K., Nguyen, T. Q. T., Le, C. N., & Wilson, R. J. S. (2018). Blue intensity from a tropical conifer’s annual rings for climate reconstruction: An ecophysiological perspective. Dendrochronologia, 50(May), 10–22. https://doi.org/10.1016/j.dendro.2018.04.003

Prairie, J., Nowak, K., Rajagopalan, B., Lall, U., & Fulp, T. (2008). A stochastic nonparametric approach for streamflow generation combining observational and paleoreconstructed data. Water Resources Research, 44(6), 1–11. https://doi.org/10.1029/2007WR006684

Prairie, J., Rajagopalan, B., Lall, U., & Fulp, T. (2007). A stochastic nonparametric technique for space-time disaggregation of streamflows. Water Resources Research, 43(3), 1–10. https://doi.org/10.1029/2005WR004721

Saito, L., Biondi, F., Devkota, R., Vittori, J., & Salas, J. D. (2015). A water balance approach for reconstructing streamflow using tree-ring proxy records. Journal of Hydrology, 529, 535–547. https://doi.org/10.1016/j.jhydrol.2014.11.022

Sauchyn, D., & Ilich, N. (2017). Nine Hundred Years of Weekly Streamflows: Stochastic Downscaling of Ensemble Tree-Ring Reconstructions. Water Resources Research, 1–18. https://doi.org/10.1002/2017WR021585


Stagge, J. H., Rosenberg, D. E., DeRose, R. J., & Rittenour, T. M. (2018). Monthly paleostreamflow reconstruction from annual tree-ring chronologies. Journal of Hydrology, 557, 791–804. https://doi.org/10.1016/j.jhydrol.2017.12.057

Stahle, D. W., Cook, E. R., Burnette, D. J., Torbenson, M. C. A., Howard, I. M., Griffin, D., Diaz, J. V., Cook, B. I., Williams, A. P., Watson, E., Sauchyn, D. J., Pederson, N., Woodhouse, C. A., Pederson, G. T., Meko, D., Coulthard, B., & Crawford, C. J. (2020). Dynamics, Variability, and Change in Seasonal Precipitation Reconstructions for North America. Journal of Climate, 33(8), 3173–3195. https://doi.org/10.1175/JCLI-D-19-0270.1

Wise, E. K. (2021). Sub-Seasonal Tree-Ring Reconstructions for More Comprehensive Climate Records in U.S. West Coast Watersheds. Geophysical Research Letters, 48(2), e2020GL091598. https://doi.org/10.1029/2020GL091598

Xu, C., Buckley, B. M., Promchote, P., Wang, S. Y. S., Pumijumnong, N., An, W., Sano, M., Nakatsuka, T., & Guo, Z. (2019). Increased Variability of Thailand’s Chao Phraya River Peak Season Flow and Its Association With ENSO Variability: Evidence From Tree Ring δ18O. Geophysical Research Letters, 46(9), 4863–4872. https://doi.org/10.1029/2018GL081458

Xu, C., Zheng, H., Nakatsuka, T., Sano, M., Li, Z., & Ge, J. (2016). Inter- and intra-annual tree-ring cellulose oxygen isotope variability in response to precipitation in Southeast China. Trees, 30(3), 785–794. https://doi.org/10.1007/s00468-015-1320-2

Xu, C., Zhu, H., Wang, S.-Y. S., Shi, F., An, W., Li, Z., Sano, M., Nakatsuka, T., & Guo, Z. (2021). Onset and maturation of Asian summer monsoon precipitation reconstructed from intra-annual tree-ring oxygen isotopes from the southeastern Tibetan Plateau. Quaternary Research, 103, 139–147. https://doi.org/10.1017/qua.2020.28


