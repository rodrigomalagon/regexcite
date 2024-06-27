
<!-- README.md is generated from README.Rmd. Please edit that file -->

# regexcite

This package is a version of the same package published for teaching
purposes by Hadley Wickham and Jennifer Bryan (see the author’s [GitHub
repository](https://github.com/jennybc/regexcite)). It features a single
function (namely, `str_split_one`) created as a toy example to work on
regular expressions (and to learn to create R packages).

This package is developed as a preparatory exercise for the module
`Data Science With R` techaed by Prof. Dr. Edzer Pebesma at the
Univeristy of Münster.

## Installation

You can install the development version of `regexcite` from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("rodrigomalagon/regexcite")
```

## Examples

The `str_split_one` function is built as a wrapper function around
`stringr::str_split()` with the benefit of border case control and
formatting of the output as a character vector rather than a list.

``` r
library(regexcite)
```

1.  Example with undesired input filtered

``` r
x <- c('a','b','c','d')
#str_split_one(x) will call an error
```

2.  Basic example to split a link from the Maxar [Open Data
    program](https://www.maxar.com/open-data) to extract the date an
    image featuring a volcanic eruption area in Tonga was captured:

``` r
(file_link <- 'https://maxar-opendata.s3.us-west-2.amazonaws.com/events/tonga-volcano21/ard/01/300222100210/2021-03-27/10300100BC131900-visual.tif')
#> [1] "https://maxar-opendata.s3.us-west-2.amazonaws.com/events/tonga-volcano21/ard/01/300222100210/2021-03-27/10300100BC131900-visual.tif"
str_split_one(file_link,'/')[9]
#> [1] "2021-03-27"
```
