HW1
================
ELisajava
2024-09-21

``` r
# Load the necessary package
library(palmerpenguins)

# Load the dataset
data("penguins", package = "palmerpenguins")

# Description of the early_january_weather dataset
names(penguins)
```

    ## [1] "species"           "island"            "bill_length_mm"   
    ## [4] "bill_depth_mm"     "flipper_length_mm" "body_mass_g"      
    ## [7] "sex"               "year"

``` r
# Get the number of rows and columns in the dataset
num_rows <- nrow(penguins)
num_cols <- ncol(penguins)

# Calculate the mean temperature
mean_temp <- mean(penguins$flipper_length_mm, na.rm = TRUE)


# Display the results
cat("penguins dataset contains the following variables:\n")
```

    ## penguins dataset contains the following variables:

``` r
cat("species","island","bill_length_mm", sep = ", ")
```

    ## species, island, bill_length_mm

``` r
cat("\n\nIt has", num_rows, "rows and", num_cols, "columns.")
```

    ## 
    ## 
    ## It has 344 rows and 8 columns.

``` r
cat("\n\nThe mean in the dataset is approximately", round(mean_temp, 2), "degrees Celsius.")
```

    ## 
    ## 
    ## The mean in the dataset is approximately 200.92 degrees Celsius.

``` r
# Load the required library if not already loaded
library(ggplot2)

# Create the scatterplot
scatterplot <- ggplot(penguins, aes(x = bill_length_mm, y = flipper_length_mm, color = species)) +
  geom_point() +
  labs(title = "Scatterplot of Flipper Length vs Bill Length",
       x = "Bill Length (mm)",
       y = "Flipper Length (mm)",
       color = "Species") +
  theme_minimal()

# Display the scatterplot
print(scatterplot)
```

    ## Warning: Removed 2 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](HW1_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->
