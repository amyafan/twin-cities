# Which U.S. Cities are the True Twins?

A quest to find the true twin cities, a response to [this challenge from the blog Math With Bad Drawings](https://mathwithbaddrawings.com/2023/12/04/data-science-contest-which-u-s-cities-are-the-true-twins/).

> Now, here comes the puzzle. It’s a two-part challenge:
> 
> * Find a complete list of all pairs of U.S. cities that meet this definition (at most 10 miles apart, with at least 200,000 people each, and populations within a factor of two).
> * From this list of twin cities, make a cogent and persuasive case for which pair deserves to be called THE twin cities.

## Data

This analysis mostly relied on 2022 Census data. All data is in the `data` folder. 

**Population data: Census population estimates**

Population estimates data were downloaded off of the Census Bureau's [city and town population](https://www.census.gov/data/tables/time-series/demo/popest/2020s-total-cities-and-towns.html#v2022) page and stored at `data/sub-est2022.csv`. 

In order to have GEOID information (our unique identifier for cities), we downloaded the data from the 2020-2022 vintage off the [FTP2 site](https://www2.census.gov/programs-surveys/popest/datasets/2020-2022/cities/totals/). The [file layout](https://www2.census.gov/programs-surveys/popest/technical-documentation/file-layouts/2020-2022/SUB-EST2022.pdf) contains information on individual variables. 

For this analysis, we only included records where the variable SUMLEV was equal to 162 (in other words, an incorporated place.)

**Location data: Census gazetteer**

The 2022 National Places Gazetteer Files were downloaded from [the Census website](https://www.census.gov/geographies/reference-files/time-series/geo/gazetteer-files.2022.html#list-tab-264479560) and stored at `data/2022_Gaz_place_national.txt`. The Census website states that: 
> The U.S. Gazetteer Files provide a listing of all geographic areas for selected geographic area types. The files include geographic identifier codes, names, area measurements, and representative latitude and longitude coordinates.

For more information about the variables, the Census website has file record layout information under the "Places" subheading [here](https://www.census.gov/programs-surveys/geography/technical-documentation/records-layout/gaz-record-layouts.2022.html#list-tab-1913338080).

**Simplemaps**

An older attempt at this challenge used the US cities database from [Simplemaps](https://simplemaps.com/data/us-cities), which is stored at `data/simplemaps_uscities_basicv1.77`.

According to their website, their dataset is built "from the ground up using authoritative sources such as the U.S. Geological Survey and U.S. Census Bureau."

The analysis using this dataset is not shown, but the results are included in the analysis notebook when narrowing down the final list of twin cities.

## Analysis

All the analysis is in `analysis.ipynb`. To merge the datasets, we used "GEOID" as the unique identifier for cities. 

The notebook has all the nitty gritty details, but in the end, I decided that **Newark, New Jersey, and Jersey City, New Jersey** were the true twin cities!