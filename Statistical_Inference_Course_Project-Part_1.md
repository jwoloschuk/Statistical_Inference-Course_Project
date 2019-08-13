Statistical Inference Course Project: Part 1
================
Jordan Woloschuk
8/13/2019

## Overview:

In this project I will investigate the exponential distribution in R and
compare it with the Central Limit Theorem.

  - The exponential distribution can be simulated in R with rexp(n,
    lambda) where lambda is the rate parameter.

  - The mean of exponential distribution is 1/lambda and the standard
    deviation is also 1/lambda.

In this project, I will set lambda = 0.2 for all of the simulations.

I will investigate the distribution of averages of 40 exponentials, and
will conduct a thousand simulations.

## Simulations:

We will first set the seed of R‘s random number generator. This is done
to create simulations or random objects that can be reproduced.

``` r
# Setting R Seed to 1 (any number would work)

set.seed(1)
```

We will next set the constants that will be used in our simulations.

``` r
# Number of simulations
numsim <- 1000

# Lamda (lambda is the rate parameter)
lamda <- 0.2

# Number of exponentials
n <- 40
```

We will run the simulation and produce a matix with 40,000 observations
(n \* numsim).

``` r
# Run the exponential simulations and populate a numsim * n matrix
Expo_Matrix <- matrix(rexp(n*numsim,lamda),nrow = numsim,ncol = n)

# Calculate the means for each row (create data.frame for ggplot)
Expo_Matrix_Means <- data.frame(expo_means = apply(Expo_Matrix,1,mean))
```

The following plot displays the distributions of exponential means.

``` r
g_expo <- ggplot(Expo_Matrix_Means, aes(expo_means)) + 
        geom_histogram(color = "navy", fill = "lightblue", binwidth = 0.25) +
        ggtitle("Distribution of Exponential Means") + 
        xlab("Means")+ylab("Frequency")

g_expo
```

![](Statistical_Inference_Course_Project-Part_1_files/figure-gfm/Expo%20Plot-1.png)<!-- -->

## Sample Mean versus Theoretical Mean:

The theoretical mean (mu) of a exponential distribution of rate lambda
is equal to the 1/lamda.

``` r
# Calculation of mu
mu <- 1/lamda
```

In our example, mu is equal to 5

While, the sample mean (X\_bar) is the average of the 1,000
simululations of the 40 sampled exponentials.

``` r
# Calculation of X_bar
X_bar <- mean(Expo_Matrix_Means$expo_means)
```

From our simulations, we calculate that X\_bar is equal to 4.9900252

As expected, the sample mean (X\_bar) adn the theoretical mean (mu) are
very similar, with an absolute difference of only 0.0099748.

## Sample Variance versus Theoretical Variance:

## Distribution:
