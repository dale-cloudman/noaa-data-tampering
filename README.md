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

For more about the dismal state of modern-day climate science, see my article, [The Vacuity of Climate Science](https://cafeamericainmag.com/the-vacuity-of-climate-science/), first published by [Café Américain](https://cafeamericainmag.com/).

## Verification

### Acquiring the Data

The data is available from the [USHCN](https://www.ncei.noaa.gov/products/land-based-station/us-historical-climatology-network) webpage:

![](https://i.imgur.com/HJRm7XE.png)

The [HTTP Access](https://www.ncei.noaa.gov/pub/data/ushcn/v2.5/) link takes us to a webpage showing the files we can download:

![](https://i.imgur.com/YUEr7wv.png)

There are four data sets, as described in their [readme](https://www.ncei.noaa.gov/pub/data/ushcn/v2.5/readme.txt):

> - tmax = monthly mean maximum temperature
> - tmin = monthly mean minimum temperature
> - tavg = average monthly temperature (tmax+tmin)/2
> - prcp = total monthly precipitation

... to be continued ...

## Response to Critiques

### Discontinued Data Set?

[@priscian](https://x.com/priscian/status/1785660913988612363) and others have argued that the USHCN dataset is deprecated, and thus irrelevant, as the official Continental US temperature data is now based on another dataset, nClimDiv:

![](https://i.imgur.com/dcGsSZa.png)

The key point is that nClimDiv uses the same homogenization and adjustment algorithms as the USHCN data set. You can see this for yourself by going to [the landing page of nClimDiv](https://www.ncei.noaa.gov/access/metadata/landing-page/bin/iso?id=gov.noaa.ncdc:C00005), clicking the [access link](https://www.ncei.noaa.gov/data/nclimdiv-monthly/access/), going up to the [parent directory](https://www.ncei.noaa.gov/data/nclimdiv-monthly/) then to the [documentation directory](https://www.ncei.noaa.gov/data/nclimdiv-monthly/doc/) and clicking on one of the documentation files, for example the [county-readme.txt](https://www.ncei.noaa.gov/data/nclimdiv-monthly/doc/county-readme.txt).

The methodology section gives us the source of the raw data:

> The Global Historical Climatology Network (GHCN) Daily dataset is the source of station data for nClimDiv.

The data that fails the *"quality assurance reviews"* is removed (set to missing):

> All GHCN-Daily stations are routinely processed through a suite of logical, serial, and spatial quality assurance reviews to identify erroneous observations.  For nClimDiv, all such data were set to missing before computing monthly values, which in turn were subjected to additional serial and spatial checks to eliminate residual outliers.

And this removed data is then filled-in using precisely the same algorithms as in the USHCN data set:

> For temperature, bias adjustments were computed to account for historical changes in observation time, **station location, temperature instrumentation, and siting conditions**.  Changes in observation time are only problematic for the COOP network whereas **changes in station location and instrumentation occur in almost all surface networks**.   As in the U.S. Historical Climatology Network version 2.5, the method of Karl et al. (1986) was applied to remove the observation time bias from the COOP network, and the **pairwise method** of Menne and Williams (2009) was used to address **changes in station location and instrumentation in all networks**.

Tellingly, however, this new data set **does not contain an equivalent `E` flag indicating infilled values**! You can verify this for yourself by reading the README in full, and looking at one of the state files for temperature data (file beginning with `climdiv-tmpcst` in the [access folder](https://www.ncei.noaa.gov/data/nclimdiv-monthly/access/)).

Thus, for convenience, we use the continuing USHCN data set as being representative of the scale of changes being used.
