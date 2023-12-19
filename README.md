# Average Carapace Length & Reef Bottom Temperatures at SBC LTER Reef Sites

**Analyzing data from 5 Santa Barbara Coastal LTER Reef sites**

Author: Anna Ramji [website]() \| [GitHub]() \| [blog post](https://a-ramji.github.io/blog/ca-spiny-lobsters/)

![](images/CA_Spiny_Lobster.jpg)

[Image credits](https://en.wikipedia.org/wiki/California_spiny_lobster#/media/File:California_Spiny_Lobster.jpg): Ed Bierman (CA, USA) - Spiny Lobster, CC BY 2.0, <https://commons.wikimedia.org/w/index.php?curid=61489279>

This repository contains the code that created data visualizations on [my blog post](https://a-ramji.github.io/blog/ca-spiny-lobsters/) about analyzing California Spiny Lobster's average carapace length and average reef bottom temperatures at 5 Santa Barbara Coastal Long Term Ecological Research Reef study sites ([SBC LTER](https://lternet.edu/site/santa-barbara-coastal-lter/) Reef).

The primary document is `ca-lobsters-blog.qmd`, which contains data, visualizations, and analysis on two primary datasets from the SBC LTER EDI collection.

## About the Data

### Dataset 1: SBC LTER: Reef: California Spiny Lobster Data

This dataset contains records on the abundance, size, and fishing effort on the California Spiny Lobster, *Panulirus interruptus*, at five SBC LTER study sites, with records from August 2012 to August 2023.

While most data was collected in the month of August at the selected study sites, there is a discrepancy that is very relevant to our analysis. - In 2014, the Arroyo Quemado Reef (site code AQUE) only had data collected in September (56 observations), and the Isla Vista Reef site (site code IVEE) had 6 carapace length observations collected in September and 114 in August of that same year.

This is relevant to our analysis because both carapace length and ocean temperatures are related to the time of year -- as more time passes, lobsters grow in size, and water temperatures fluctuate seasonally, as shown in this data visualization of monthly mean temperatures from Shore Stations (one of the Scripps Institution of Oceanography's programs that works to collect daily temperature (SST) and salinity records at sites along the California coast from La Jolla to Trinidad).

Notes on methods, limitations: "Transects were sampled by two SCUBA divers during daylight hours" -- this is notable because lobsters are most active at night, which may add further limitations on the ability of the sample of the population, so any conclusions we come to based on our analysis of these data may not have as much significance or strength in our ability to make claims about the true population.

**Data Citation:**

Reed, D. & Miller, R. (2023). *SBC LTER: Reef: Abundance, size and fishing effort for California Spiny Lobster (Panulirus interruptus), ongoing since 2012 ver 9*. [Data File]. Environmental Data Initiative. <https://doi.org/10.6073/pasta/3595322687af94cd532620ad9db94c77> (Accessed 2023-11-22).

### Dataset 2: SBC LTER: Reef: Bottom Temperature Data

This dataset contains records of the water temperature at the bottom (or a relatively low, non-surface depth) at nine of the SBC LTER Reef study sites in 15 minute intervals beginning in 2000 up to July 4th, 2023. I accessed this continuous water temperature dataset via the [EDI Data Portal](https://portal.edirepository.org/nis/metadataviewer?packageid=knb-lter-sbc.13.29). The primary data file on this portal is a .csv, which is 372.8 MB. The key variables that I'll be using in this data set are:

-   **Site_code** (default column name: SITE), contains a string of the name of the field site that each measurement was taken at. Note that the depth of temperature logger at each site varies from 4.95 to 8.15 meters.
-   **date** (default column name: DATE_LOCAL), contains the date of observation in the format YYYY-MM-DD
-   **Temperature in Celsius** (default column name: TEMP_C): Ambient water temperature, measured with Onset tidbit. "tidbit" refers to the measurement instrument, a 32K StowAway TidbiT (-5 deg C to 37 deg C) manufactured by Onset Computer Corporation.

The NA code for this dataset is `-99999`.

You can download the data using [this link](https://portal.edirepository.org/nis/dataviewer?packageid=knb-lter-sbc.13.29&entityid=d707a45a2cd6eee1d016d99844d537da), or you can copy and paste that download link directly into your `read_csv()` function as I did.

**Data Citation:**

Santa Barbara Coastal LTER, D. Reed, and R. Miller. (2023). *SBC LTER: Reef: Bottom Temperature: Continuous water temperature, ongoing since 2000 ver 29*. [Data File]. Environmental Data Initiative. <https://doi.org/10.6073/pasta/3071d4179516b5ae56018bfa03fea9dd> (Accessed 2023-12-03).
