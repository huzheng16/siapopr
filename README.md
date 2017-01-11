
<!-- README.md is generated from README.Rmd. Please edit that file -->
siapopr
=======

siapopr is an R package that wraps the C++ functions SIApop. These functions simulate birth-death-mutation processes with mutations having random fitnesses to simulate clonal evolution.

Dependencies
------------

-   [GNU Scientific Library](https://www.gnu.org/software/gsl/)
    -   `brew install gsl` with Homebrew on OSX or from [here](http://ftpmirror.gnu.org/gsl/).
    -   On windows, download and extract the file [local\#\#\#.zip](http://www.stats.ox.ac.uk/pub/Rtools/goodies/multilib/) and create an environmental variable LIB\_GSL to add the directory.
    -   On Linux install libgsl0-dev and gsl-bin.
-   [Rcpp](https://github.com/RcppCore/Rcpp)
-   \[devtools\]
    -   `install.packages(devtools)`

Recommended packages
--------------------

-   [ggmuller](https://github.com/robjohnnoble/ggmuller)
    -   `devtools::install_github("robjohnnoble/ggmuller")`
-   [fishplot](https://github.com/chrisamiller/fishplot)
    -   `devtools::install_github("chrisamiller/fishplot")`

Uses
====

SIApop (Simulating Infinite-Allele populations) is a set of standalone C++ programs to simulate homogeneous and inhomogeneous stochastic branching processes under a very flexible set of assumptions. The software simulates clonal evolution with the emergence of driver and passenger mutations under the infinite-allele assumption. The software is an application of the Gillespie Stochastic Simulation Algorithm expanded to a large number of cell types and scenarios, with the intention of allowing users to easily modify existing models or create their own. Visualization functions in R are included to show results of individual simulations.

A branching process is a stochastic process used to model the growth and composition of reproducing populations. Assumptions made in branching processes are individuals live for a random amount of time before splitting into a random number of individuals (both dictated by distribution functions). Individuals of the same type are independent and identically distributed. These processes are useful for modeling cell growth and evolution, as in a tumor.

Three difference executables are included based on the type of simulation desired. A birth-death process with no mutations has a closed-form distribution, and is simulated without the Gillespie algorithm with SIApop-simple. The constant rate birth-death processes that allows for mutation can be simulated with SIApop. SIApop-td is used to model processes where birth and death rates may change as a function of time.