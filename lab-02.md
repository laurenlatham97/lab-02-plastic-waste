Lauren Latham - Lab 02 - Plastic waste
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

### Exercise 1 - distribution of plastic waste faceted by continent

Below is a histogram of the distribution of plastic waste per capita
faceted by continent. The histogram reveals that North America contains
the countries that have the most plastic waste per capita. Additionally,
the distribution seems to be positively skewed for most continents.

``` r
ggplot(plastic_waste, aes(x=plastic_waste_per_cap,))+geom_histogram(bins=30)+facet_wrap(~continent)
```

    ## Warning: Removed 51 rows containing non-finite values (stat_bin).

![](lab-02_files/figure-gfm/plot-plastic_waste-1.png)<!-- -->

### Exercise 2 - density plot of pastic waste per capita

Below is a density plot demonstrating plastic waste per capita with each
continent color-coded. I lowered the alpha to 0.3 so that data from each
continent can be seen more easily. The color and fill go in the mapping
aesthetics because they are mapped to specific variables, whereas the
alpha information goes in the geom characteristics because it is
information that is used in the same way for each variable (i.e., each
continent).

``` r
ggplot(plastic_waste, aes(x=plastic_waste_per_cap, color=continent, fill=continent))+geom_density(alpha=.3)
```

    ## Warning: Removed 51 rows containing non-finite values (stat_density).

![](lab-02_files/figure-gfm/plot-pastic_waste%202-1.png)<!-- -->

### Exercise 3 - box plots and violin plots

Below are side by side box plots displaying plastic waste per capita for
each continent:

``` r
ggplot(data = plastic_waste, 
       mapping = aes(x = continent, 
                     y = plastic_waste_per_cap)) +
  geom_boxplot()
```

    ## Warning: Removed 51 rows containing non-finite values (stat_boxplot).

![](lab-02_files/figure-gfm/plot-pastic_waste%203-1.png)<!-- -->

And violin plots…

``` r
ggplot(data = plastic_waste, 
       mapping = aes(x = continent, 
                     y = plastic_waste_per_cap)) +
  geom_violin()
```

    ## Warning: Removed 51 rows containing non-finite values (stat_ydensity).

![](lab-02_files/figure-gfm/plot-pastic_waste%204-1.png)<!-- -->

The violin plots are useful because the display the full distribution of
the data, unlike the box plots. For example, a bimodal distribution is
very easily obscured by box plots. Box plots however make it easier to
discern certain summary statistics (median, upper and lower quartile,
outliers).

### Exercise 4 - scatterplots

Relationship between plastic waste per capita and mismanaged plastic
waste per capita (scatterplot):

``` r
ggplot(data = plastic_waste, 
       mapping = aes(x = plastic_waste_per_cap, 
                     y = mismanaged_plastic_waste_per_cap)) +
  geom_point()
```

    ## Warning: Removed 51 rows containing missing values (geom_point).

![](lab-02_files/figure-gfm/plot-pastic_waste%205-1.png)<!-- -->

From the above scatterplot we can see that there is a positive
relationship between plastic waste per capita and mismanaged plastic
wast per capita (i.e., as plastic waste per capita goes up, mismanaged
plastic waster per capita also goes up). However, it looks like there
may be two slightly different patterns, with some countries having a
very strong positive relationship between these variables, and other
countries have a somewhat weaker positive relationship.

Relationship between plastic waste per capita and mismanaged plastic
waste per capita (scatterplot-color country):

``` r
ggplot(data = plastic_waste, 
       mapping = aes(x = plastic_waste_per_cap, 
                     y = mismanaged_plastic_waste_per_cap, color = continent)) +
  geom_point()
```

    ## Warning: Removed 51 rows containing missing values (geom_point).

![](lab-02_files/figure-gfm/plot-pastic_waste%206-1.png)<!-- -->

The above scatterplot demonstrates the same relationship described
earlier between plastic waste per capita and mismanaged plastic waste
per capita, but the color coding makes it easier to understand the two
potentially different patterns. It looks like the relationship between
these variables is weaker for North American and European countries, and
much stronger for other countries.

Relationship between total population and plastic waste per capita
(scatterplot):

``` r
ggplot(data = plastic_waste, 
       mapping = aes(x = total_pop, 
                     y = plastic_waste_per_cap, color = continent)) +
  geom_point()
```

    ## Warning: Removed 61 rows containing missing values (geom_point).

![](lab-02_files/figure-gfm/plot-pastic_waste-1.png)<!-- -->

Relationship between coastal population and plastic waste per capita
(scatterplot):

``` r
ggplot(data = plastic_waste, 
       mapping = aes(x = coastal_pop, 
                     y = plastic_waste_per_cap, color = continent)) +
  geom_point()
```

    ## Warning: Removed 51 rows containing missing values (geom_point).

![](lab-02_files/figure-gfm/plot-pastic_waste%207-1.png)<!-- -->

Neither total population nor coastal population appear to be strongly
linearly associated with plastic waste per capita. It’s somewhat
difficult to tell however, because many of the countries cluster around
the same total population and coastal population. Interestingly, a lot
of the Asian countries with very large coastal populations seem to be
relatively low in plastic waster per capita, this is less true however
for total population. The Oceanic and NOrth American countries however
with lower coastal population and total population seem to fall pretty
high in plastic waste per capita.
