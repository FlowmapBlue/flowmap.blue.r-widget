

# Flowmap.blue R widget

<!-- badges: start -->

<a
href="https://github.com/FlowmapBlue/flowmapblue.R/actions/workflows/R-CMD-check.yaml"
target="_blank"><img
src="https://github.com/FlowmapBlue/flowmapblue.R/actions/workflows/R-CMD-check.yaml/badge.svg"
alt="R-CMD-check" /></a> <!-- badges: end -->

WORK IN PROGRESS

This is a [Flowmap.blue](https://flowmap.blue) widget for R. It produces
an interactive flow map representing numbers of movements between
locations (origin-destination data).wn

You might also consider using this pure R flowmapping library:
https://github.com/JohMast/flowmapper

![](man/figures/demo.png)

As an alternative, you may also consider using R to populate a
spreadsheet for publishing on [Flowmap.blue](https://flowmap.blue) as
described in this [excellent blog
post](https://doodles.mountainmath.ca/blog/2020/01/06/flow-maps/).

### Installation

From CRAN (when available):

``` r
# install.packages("flowmapblue")
```

To install from GitHub you will need to install `remotes` if you don’t
have it yet:

``` r
if (!require("remotes")) install.packages("remotes")

remotes::install_github("FlowmapBlue/flowmapblue.R",
  force = TRUE, dependencies = TRUE)
```

### Quick example

``` r
Sys.setenv(MAPBOX_API_TOKEN = "YOUR_MAPBOX_ACCESS_TOKEN")

locations <- read.csv(system.file("extdata/example/locations.csv", package = "flowmapblue"))

flows <- read.csv(system.file("extdata/example/flows.csv", package = "flowmapblue"))

flowmap <- flowmapblue(
 locations,
 flows,
 mapboxAccessToken = Sys.getenv('MAPBOX_API_TOKEN'),
 clustering = TRUE,
 darkMode = TRUE,
 animation = FALSE
)

# view the map
flowmap
```

Here is a [nice intro blog
post](https://www.paulamoraga.com/blog/2020-07-11-mobility.html) by
Paula Moraga.

For more examples with time and date in flows data, as well as
integration with Shiny, see the Quick Start vignette and documentation
for the package functions.
