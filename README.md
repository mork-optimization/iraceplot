
# The iraceplot package

<!-- badges: start -->
[![R-CMD-check](https://github.com/auto-optimization/iraceplot/workflows/R-CMD-check/badge.svg)](https://github.com/auto-optimization/iraceplot/actions)
<!-- badges: end -->

**Maintainers:** Leslie Pérez Cáceres, [Manuel López-Ibáñez](http://lopez-ibanez.eu)

**Creators:** Pablo Oñate Marín, Leslie Pérez Cáceres, [Manuel López-Ibáñez](http://lopez-ibanez.eu)

**Contact:** <https://groups.google.com/d/forum/irace-package>

---------------------------------------

Introduction
============

The iraceplot package provides a set of functions that create different plots to visualize
the data generated by the irace configurator (https://cran.r-project.org/web/packages/irace/index.html).

This package provides allows to visualize:

- Configurations generated by irace (elite and non-elite)
- Elite configurations performance (training and testing)
- Parameter values and sampling distributions
- Configuration process overview

Also, the package allows to create a small HTML report summarizing relevant information obtained during the execution of irace.

The aim of this package it to provide support for the analysis of the best parameter settings found, the assessment of the parameter space explored by irace and, the overall performance of the configuration process. Such analyses might lead to insights about the role of algorithmic components their interactions, or to improve the configuration process itself.

**Keywords:** automatic configuration, offline tuning, parameter tuning, parameter visualization, irace.


Requisites
--------------

 * R (<https://www.r-project.org>) is required for running irace and to use iraceplot, but
   you don't need to know the R language to use any of them.

User guide
----------

A [user guide](https://auto-optimization.github.io/iraceplot/articles/iraceplot_package.html)
comes with the package. The following is a quick-start guide. The user guide gives more detailed
instructions.



Installing R
============

The official instructions are available at
<https://cran.r-project.org/doc/manuals/r-release/R-admin.html>. We give below
a quick R installation guide that will work in most cases.

GNU/Linux
---------

You should install R from your package manager. On a Debian/Ubuntu system it
will be something like:

    $ sudo apt-get install r-base

Once R is installed, you can launch R from the Terminal and from the R
prompt install the iraceplot package. See instructions below.


OS X
----

You can install R directly from a CRAN mirror
(<https://cran.r-project.org/bin/macosx/>).

Alternatively, if you use homebrew, you can just brew the R formula
from the science tap (unfortunately it does not come already bottled
so you need to have Xcode installed to compile it):

```bash
    $ brew tap homebrew/science
    $ brew install r
```

Once R is installed, you can launch R from the Terminal (or from your
Applications), and from the R prompt install the iraceplot package. See
instructions below.

Windows
-------

You can install R from a CRAN mirror
(<https://cran.r-project.org/bin/windows/>). Once R is installed, you can
launch the R console and install the iraceplot package from it. See instructions
below.



Installing the iraceplot package
============================

1. Install within R (automatic download):
For installing iraceplot you need to install the devtools package:

``` r
install.packages("devtools")
```
Currently, the iraceplot package can be installed from Gtihub:

``` r
devtools::install_github("auto-optimization/iraceplot")

```
2. Manually
   [download the package from CRAN]()
   and invoke at the command-line:
```bash
        $ R CMD INSTALL <package>
```
   where `<package>` is one of the three versions available: `.tar.gz`
   (Unix/BSD/GNU/Linux), `.tgz` (MacOS X), or `.zip` (Windows).
   

How To Use
===========================

Load the package in the R console:

``` r
library(iraceplot)
```

Load the log file generated by irace (.Rdata) for example, replace the path to your irace.Rdata file in the following line:

``` r
load("~/patch/example/name.Rdata")
```
 
Once the data is loaded in the console, you should be able to access the `iraceResults` object. List the
objects currently loaded to verify that `iraceResults` is loaded:
``` r
ls()
```

Check the [documentation](https://auto-optimization.github.io/iraceplot/reference/index.html) and the [user guide] (https://auto-optimization.github.io/iraceplot/articles/iraceplot_package.html) to find the plot most suited to your needs or generate a general-purpose report with:

``` r
iraceplot::report(iraceResults, "path/to/my_report")
```
