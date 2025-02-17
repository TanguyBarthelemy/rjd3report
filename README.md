
<!-- README.md is generated from README.Rmd. Please edit that file -->

# rjd3report

<!-- <img src="man/figures/logo.png" align="right" /> -->
<!-- [![R-CMD-check](https://github.com/AQLT/rjdqa/workflows/R-CMD-check/badge.svg)](https://github.com/AQLT/rjdqa/actions) -->
<!-- [![CRAN_Status_Badge](http://www.r-pkg.org/badges/version/rjdqa)](https://cran.r-project.org/package=rjdqa) -->
<!-- [![CRAN last release](http://www.r-pkg.org/badges/last-release/rjdqa)](https://cran.r-project.org/package=rjdqa) -->
<!-- [![CRAN monthly downloads](http://cranlogs.r-pkg.org/badges/rjdqa?color=lightgrey)](https://cran.r-project.org/package=rjdqa) -->
<!-- [![CRAN downloads](http://cranlogs.r-pkg.org/badges/grand-total/rjdqa?color=lightgrey)](https://cran.r-project.org/package=rjdqa) -->

## Overview

rjd3report is an extension of the R packages around JDemetra+ 3.0
available at <https://github.com/rjdemetra/rjdemetra> The rjd3report
package provides help to the quality assessment by producing different
dashboards.

## Installation

rjd3report requires Java SE 17 or later version.

``` r
# Install development version from GitHub
# install.packages("devtools")
remots::install_github("AQLT/rjd3report")
```

If you have troubles with the installation of RJDemetra or rjdqa, check
the [installation
manual](https://github.com/jdemetra/rjdemetra/wiki/Installation-manual).

# Usage

<!-- ## Create Statistics Canada dashboard -->
<!-- The function `sa_dashboard()` reproduces Statistics Canada dashboard. -->
<!-- See : -->
<!-- KIRCHNER R., LADIRAY D., MAZZI G. L. (2018), "Quality Measures and Reporting for Seasonal Adjustment", edited by G. L. Mazzi, co-edited by D. Ladiray, European Union, Luxembourg. <https://ec.europa.eu/eurostat/web/products-manuals-and-guidelines/-/KS-GQ-18-001> -->
<!-- MATTHEWS S. (2016), "Quality Assurance of Seasonal Adjustment for a Large System of Time Series", 36th International Symposium on Forecasting Santander, Spain. -->
<!-- ```{r stat_cana_dash, fig.height = 8, fig.width = 10} -->
<!-- library(RJDemetra) -->
<!-- library(rjdqa) -->
<!-- sa_model <- x13(ipi_c_eu[, "FR"], "RSA5c") -->
<!-- dashboard_data <- sa_dashboard(sa_model) -->
<!-- plot(dashboard_data, main = "Statistics Canada dashboard", -->
<!--      subtitle = "SA with X13") -->
<!-- ``` -->

## Simple dashboard

``` r
library(rjd3report)
y <- rjd3toolkit::ABS$X0.2.09.10.M
sa_mod <- rjd3x13::x13(y)
dashboard_data <- simple_dashboard(sa_mod)
plot(dashboard_data, main = "Simple dashboard")
```

<img src="man/figures/README-simple_dash-1.png" style="display: block; margin: auto;" />

``` r
dashboard_data2 <- simple_dashboard2(sa_mod)
plot(dashboard_data2, main = "Simple dashboard with outlier")
```

<img src="man/figures/README-simple_dash-2.png" style="display: block; margin: auto;" />
