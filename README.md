# NOAA Data Tampering

The [National Oceanic and Atmospheric Administration](https://www.noaa.gov/) (NOAA) publishes US temperature data as part of its regular course of operations.

The [U.S. Historical Climatology Network (USHCN) data](https://www.ncei.noaa.gov/products/land-based-station/us-historical-climatology-network) is one of the longest-running and highest-quality temperature records, and is vital for understanding the Earth's climate.

However, NOAA does not simply publish the measurements that the climate stations report. It also adjusts them with a "Pairwise Homogeneity Algorithm". 

This is not a secret, but it's perhaps not well-known just how much of the data is altered. The percent of altered data is increasing each year and **surpassed 50%** in 2023:

![](https://pbs.twimg.com/media/GMUe53PaEAAVKQh?format=png&name=small)

(source: [@TonyHeller](https://x.com/TonyClimate/status/1784866882266533945))

I have verified this for myself. The calculation is easy to do with a small bit of programming knowledge, and this repository is meant to contain end-to-end instructions and explanations so everybody can see for themselves that the extent of this data-alteration is factual, and not hyperbolic. 

It is also relevant to note that the adjustments [nearly perfectly correlate with rising CO2 levels](https://realclimate.science/2014/10/02/co2-drives-ncdc-data-tampering/#gsc.tab=0). That is to say, the more CO2 levels have risen, the more the data is **adjusted** to show warmer temperatures. Thus the recent warming trend that has been attributed to human activity appears to be a fabrication rather than a fact.

For more details about this homogenization algorithm, see this [2022 study](https://globalwarmingsolved.com/2022/02/22/major-problems-identified-in-the-data-adjustments-applied-to-a-widely-used-global-temperature-dataset/) that identified several major problems with is, such as inconsistency (i.e. running the algorithm multiple times gives different results) and lack of correspondence to reality (i.e. the computationally-derived adjustments don't correspond to any actual changes at the weather stations).

## Verification (Placeholder)

This section remains a placeholder. It shall be filled in at a later date.

For more about the dismal state of modern-day climate science, see my article, [The Vacuity of Climate Science](https://cafeamericainmag.com/the-vacuity-of-climate-science/), first published by [Café Américain](https://cafeamericainmag.com/).
