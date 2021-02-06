Lab 02 - Plastic waste
================
laurenlatham97
2/4/21

## Load packages and data

``` r
library(tidyverse) 
```

``` r
plastic_waste <- read_csv("data/plastic-waste.csv")
```

## Exercises

### Exercise 1

Remove this text, and add your answer for Exercise 1 here.

``` r
# insert code here
```

Below is a histogram of the distribution of plastic waste per capita
faceted by continent. WHAT DOES THIS SAY ABOUT HOW CONTINENTS COMPARE TO
EACHOTHER??

``` r
ggplot(plastic_waste, aes(x=plastic_waste_per_cap))+geom_histogram(bins=15)+facet_wrap(~continent)
```

    ## Warning: Removed 51 rows containing non-finite values (stat_bin).

![](lab-02_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

Below is a density plot demonstrating plastic waste per capita with each
continent color-coded. I lowered the alpha to 0.3 data from each
continent can be seen more easily. The color and fill go in the mapping
aesthetics because they are mapped to specific variables, whereas the
alpha information goes in the geom characteristics because it is
information that is used in the same way for each variable (i.e., each
continent).

``` r
ggplot(plastic_waste, aes(x=plastic_waste_per_cap, color=continent, fill=continent))+geom_density(alpha=.3)
```

    ## Warning: Removed 51 rows containing non-finite values (stat_density).

![](lab-02_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

### Exercise 2

``` r
# insert code here
```

### Exercise 3

Remove this text, and add your answer for Exercise 3 here.

### Exercise 4

Remove this text, and add your answer for Exercise 4 here.

``` r
# insert code here
```

### Exercise 5

Remove this text, and add your answer for Exercise 5 here.

``` r
# insert code here
```

### Exercise 6

Remove this text, and add your answer for Exercise 6 here.

``` r
# insert code here
```

### Exercise 7

Remove this text, and add your answer for Exercise 7 here.

``` r
# insert code here
```

``` r
# insert code here
```

### Exercise 8

Remove this text, and add your answer for Exercise 8 here.

``` r
# insert code here
```
