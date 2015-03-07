## Data for No Ceilings: The Full Participation Project

This is a repository of the data behind the [No Ceilings](http://noceilings.org) site. Please use http://noceilings.org/data when linking to this page. 

> In 1995, at the UN Fourth World Conference on Women in Beijing, leaders from governments and civil society around the world came together and committed to ensuring that women and girls have the opportunity to participate fully in all aspects of life.

> This year marks the 20th anniversary of that moment. The Bill & Melinda Gates Foundation and the No Ceilings initiative of the Bill, Hillary & Chelsea Clinton Foundation have joined forces to gather data and analyze the gains made for women and girls over the last two decades, as well as the gaps that remain.

> This site and The Full Participation Report are the result—home to 850,000 data points, spanning more than 20 years, from over 190 countries. Through data visualizations and stories, we aim to present the gains and gaps in understandable, sharable ways—including by making the data open and easily available.

Learn more about the No Ceilings project [here](http://noceilings.org/about). 

One of the most important aspects of this project is the compilation and collation of such a large number of statistics into a single location. We'd like to encourage students, researchers, hobbyists, and other interested parties to do their own analyses and visualizations on topics they care about.


### Indicators

The data consists of ~900 topics (referred to as "indicators"), each of which covers a focus area across a set of years and a list of countries.

The list of indicators is available in several formats: [HTML](http://htmlpreview.github.com/?https://raw.githubusercontent.com/fathominfo/noceilings-data/master/indicators.html), [Markdown](https://github.com/fathominfo/noceilings-data/blob/master/indicators.md), [CSV](https://raw.githubusercontent.com/fathominfo/noceilings-data/master/indicators.csv), and [JSON](https://raw.githubusercontent.com/fathominfo/noceilings-data/master/indicators.json). 

The data is collected from many sources. They can be seen in the *source* column. Data from noceilings.org that lists *WORLD Policy Analysis Center* as the source has additional restrictions on its use and therefore is not available as part of this repository. Visit [their site](http://worldpolicyforum.org/noceilings) for more information.


### Explanation of the indicators file

The *primary*, *secondary*, and *tertiary* columns are used in [the map](http://noceilings.org/map) to organize the indicators into something that can be reasonably browsed. Instead of presenting users with ~900 entries topics, they're first grouped by *theme*. Next, there's a *primary* name (seen on the map as the title at the top). 

For instance, for the indicator named [Gross enrollment ratio in secondary school, female](http://noceilings.org/map/#GERSFEIN&2012):
 * the *primary* category is *Gross enrollment ratio*
 * the *secondary* is *secondary school* 
 * and the *tertiary* is *female*

The *flavor* column is either *num* or a semicolon-separated list of variants for this entry. In the [indicators.json]() file, this is an anachronism from the process of how the data was integrated (from the CSV files). In future releases, this property won't be present (or will be set to null) for numeric data, and list the variants in an array (rather than requiring the split() call).

For instance, for the indicator titled "Can married women pursue a trade or profession in the same way as a man?" [see here](http://noceilings.org/map/#MWPTPWBL), the variants are listed in the *flavor* column as `Yes;No;Other`.


### Individual data files

This repository includes ~900 indicators, each in single files in both CSV and JSON format. Most data are between the years 1995-2014, but some data has 1990 entries, often for an indicator available in five year intervals: 1990, 1995, 2000... 


##### CSV format

The columns of the CSV file are first the 3-digit ISO code (see below) for the country represented, followed by a column for each year in the data set. 

Check out the [enrollment](https://raw.githubusercontent.com/fathominfo/noceilings-data/master/csv/GERSFEIN.csv) and [profession](https://raw.githubusercontent.com/fathominfo/noceilings-data/master/csv/MWPTPWBL.csv) data mentioned in the previous section for examples.

Note that while the columns are in order from oldest to most recent, they may skip years if no data is available. Because the data is often quite sparse, columns are simply omitted.


##### JSON format

Each file contains a single JSON object. Inside, a hash maps each 3-digit country code (see below) to another hash mapping each year to the value for that year. Years with no data are not included.

Again, the [enrollment](https://raw.githubusercontent.com/fathominfo/noceilings-data/master/json/GERSFEIN.json) and [profession](https://raw.githubusercontent.com/fathominfo/noceilings-data/master/json/MWPTPWBL.json) data files. To save space (these are the same files used on the production server), the JSON files aren't beautified. 


### Countries and regions

To map a country from a 3-letter ISO code to its name, use [this list](https://raw.githubusercontent.com/fathominfo/noceilings-data/master/countries.csv) (CSV format). The first column is the 3-digit code, the second column is the full country name. For some longer country names that fit poorly in the interface, a third column is present with the name used on the site. 

explanation of the regional groupings
regional groupings file

### Additional background

We (Fathom) received this data in a pair of flat files (one for numeric, one non-numeric). Where possible, we've corrected some errors, grouped the data into categories (the theme, primary, secondary, and tertiary columns), and are making this available in an accessible format to be usable for other projects. 
