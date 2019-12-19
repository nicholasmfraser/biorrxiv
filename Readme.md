
<!-- README.md is generated from README.Rmd. Please edit that file -->

# biorrxiv

R client for interacting with the [bioRxiv API](https://api.biorxiv.org)

\*\* This is a (very incomplete) work in progress \*\*

## Installation

Install the development version from Github:

``` r
install.packages("devtools")
devtools::install_github("nicholasmfraser/biorrxiv")
```

## Usage

The main functions in `biorrxiv` loosely conform to the API endpoints
outlined in the API documentation [see here](https://api.biorxiv.org/).

### Content detail

Retrieve details of either a set of preprints deposited between two
dates, or lookup a single preprint by DOI.

``` r
# Get details of preprints deposited between 2017-01-01 and 2017-01-10
# By default, only the first 100 records are returned
biorrxiv_content(from = "2018-01-01", to = "2018-01-10")

# Define a limit to return more than 100 records
biorrxiv_content(from = "2018-01-01", to = "2018-01-10", limit = 200)

# Or set limit as "*" to return all records
biorrxiv_content(from = "2018-01-01", to = "2018-01-10", limit = "*")

# Skip the first 100 records
biorrxiv_content(from = "2018-01-01", to = "2018-01-10", limit = 200, skip = 100)

# By default, data is returned in a list. Use the "format" argument to specify
# that data should be returned in "json" format or as a data frame ("df").
biorrxiv_content(from = "2018-01-01", to = "2018-01-10", format = "df")
```
