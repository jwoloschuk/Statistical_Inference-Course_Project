Statistical Inference Course Project: Part 2
================
Jordan Woloschuk
8/13/2019

## Overview:

In this project I will analyze the ToothGrowth data contianed withing
the R datasets package. This analysis will include four (4) main steps.

  - Load the ToothGrowth data and perform some basic exploratory data
    analyses
  - Provide a basic summary of the data.
  - Use confidence intervals and/or hypothesis tests to compare tooth
    growth by supp and dose.
  - State your conclusions and the assumptions needed for your
    conclusions.

## Load the ToothGrowth Data

In this section we will load the ToothGrowth data and perform some basic
exploratory data analyses.

``` r
# Load ToothGrowth
data("ToothGrowth")

# Set the dose as a factor instead of the default num class
ToothGrowth$dose <- as.factor(ToothGrowth$dose)
```

## Summary of the ToothGrowth data

In this section we will provide a basic summary of the ToothGrowth data.

``` r
# Use str to display the structure of the data
str(ToothGrowth)
```

    ## 'data.frame':    60 obs. of  3 variables:
    ##  $ len : num  4.2 11.5 7.3 5.8 6.4 10 11.2 11.2 5.2 7 ...
    ##  $ supp: Factor w/ 2 levels "OJ","VC": 2 2 2 2 2 2 2 2 2 2 ...
    ##  $ dose: Factor w/ 3 levels "0.5","1","2": 1 1 1 1 1 1 1 1 1 1 ...

``` r
# Use summary to display a summary of the data
summary(ToothGrowth)
```

    ##       len        supp     dose   
    ##  Min.   : 4.20   OJ:30   0.5:20  
    ##  1st Qu.:13.07   VC:30   1  :20  
    ##  Median :19.25           2  :20  
    ##  Mean   :18.81                   
    ##  3rd Qu.:25.27                   
    ##  Max.   :33.90

``` r
# Use head and tail to show the first six (6) and last six(6) rows of data.
head(ToothGrowth)
```

    ##    len supp dose
    ## 1  4.2   VC  0.5
    ## 2 11.5   VC  0.5
    ## 3  7.3   VC  0.5
    ## 4  5.8   VC  0.5
    ## 5  6.4   VC  0.5
    ## 6 10.0   VC  0.5

``` r
tail(ToothGrowth)
```

    ##     len supp dose
    ## 55 24.8   OJ    2
    ## 56 30.9   OJ    2
    ## 57 26.4   OJ    2
    ## 58 27.3   OJ    2
    ## 59 29.4   OJ    2
    ## 60 23.0   OJ    2
