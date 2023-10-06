Mini Data Analysis - Deliverable 1
================
Juliana\
2023-10-06

---
# Welcome to your (maybe) first-ever data analysis project!

And hopefully the first of many. Let's get started:

1.  Install the [`datateachr`](https://github.com/UBC-MDS/datateachr) package by typing the following into your **R terminal**:

<!-- -->

```         
install.packages("devtools")
devtools::install_github("UBC-MDS/datateachr")
```

2.  Load the packages below.


```r
library(datateachr)
library(tidyverse)
```

```
## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
## ✔ dplyr     1.1.3     ✔ readr     2.1.4
## ✔ forcats   1.0.0     ✔ stringr   1.5.0
## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
## ✔ purrr     1.0.2     
## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
## ✖ dplyr::filter() masks stats::filter()
## ✖ dplyr::lag()    masks stats::lag()
## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors
```

3.  Make a repository in the <https://github.com/stat545ubc-2023> Organization. You can do this by following the steps found on canvas in the entry called [MDA: Create a repository](https://canvas.ubc.ca/courses/126199/pages/mda-create-a-repository). One completed, your repository should automatically be listed as part of the stat545ubc-2023 Organization.

# Instructions

## For Both Milestones

-   Each milestone has explicit tasks. Tasks that are more challenging will often be allocated more points.

-   Each milestone will be also graded for reproducibility, cleanliness, and coherence of the overall Github submission.

-   While the two milestones will be submitted as independent deliverables, the analysis itself is a continuum - think of it as two chapters to a story. Each chapter, or in this case, portion of your analysis, should be easily followed through by someone unfamiliar with the content. [Here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/) is a good resource for what constitutes "good code". Learning good coding practices early in your career will save you hassle later on!

-   The milestones will be equally weighted.

## For Milestone 1

**To complete this milestone**, edit [this very `.Rmd` file](https://raw.githubusercontent.com/UBC-STAT/stat545.stat.ubc.ca/master/content/mini-project/mini-project-1.Rmd) directly. Fill in the sections that are tagged with `<!--- start your work below --->`.

**To submit this milestone**, make sure to knit this `.Rmd` file to an `.md` file by changing the YAML output settings from `output: html_document` to `output: github_document`. Commit and push all of your work to the mini-analysis GitHub repository you made earlier, and tag a release on GitHub. Then, submit a link to your tagged release on canvas.

**Points**: This milestone is worth 36 points: 30 for your analysis, and 6 for overall reproducibility, cleanliness, and coherence of the Github submission.

# Learning Objectives

By the end of this milestone, you should:

-   Become familiar with your dataset of choosing
-   Select 4 questions that you would like to answer with your data
-   Generate a reproducible and clear report using R Markdown
-   Become familiar with manipulating and summarizing your data in tibbles using `dplyr`, with a research question in mind.

# Task 1: Choose your favorite dataset

The `datateachr` package by Hayley Boyce and Jordan Bourak currently composed of 7 semi-tidy datasets for educational purposes. Here is a brief description of each dataset:

-   *apt_buildings*: Acquired courtesy of The City of Toronto's Open Data Portal. It currently has 3455 rows and 37 columns.

-   *building_permits*: Acquired courtesy of The City of Vancouver's Open Data Portal. It currently has 20680 rows and 14 columns.

-   *cancer_sample*: Acquired courtesy of UCI Machine Learning Repository. It currently has 569 rows and 32 columns.

-   *flow_sample*: Acquired courtesy of The Government of Canada's Historical Hydrometric Database. It currently has 218 rows and 7 columns.

-   *parking_meters*: Acquired courtesy of The City of Vancouver's Open Data Portal. It currently has 10032 rows and 22 columns.

-   *steam_games*: Acquired courtesy of Kaggle. It currently has 40833 rows and 21 columns.

-   *vancouver_trees*: Acquired courtesy of The City of Vancouver's Open Data Portal. It currently has 146611 rows and 20 columns.

**Things to keep in mind**

-   We hope that this project will serve as practice for carrying our your own *independent* data analysis. Remember to comment your code, be explicit about what you are doing, and write notes in this markdown document when you feel that context is required. As you advance in the project, prompts and hints to do this will be diminished - it'll be up to you!

-   Before choosing a dataset, you should always keep in mind **your goal**, or in other ways, *what you wish to achieve with this data*. This mini data-analysis project focuses on *data wrangling*, *tidying*, and *visualization*. In short, it's a way for you to get your feet wet with exploring data on your own.

And that is exactly the first thing that you will do!

1.1 **(1 point)** Out of the 7 datasets available in the `datateachr` package, choose **4** that appeal to you based on their description. Write your choices below:

**Note**: We encourage you to use the ones in the `datateachr` package, but if you have a dataset that you'd really like to use, you can include it here. But, please check with a member of the teaching team to see whether the dataset is of appropriate complexity. Also, include a **brief** description of the dataset here to help the teaching team understand your data.

<!-------------------------- Start your work below ---------------------------->

> Selected datasets:
> 1. apt_buildings 
> 2. flow_sample 
> 3. cancer_sample 
> 4. vancouver_trees

<!----------------------------------------------------------------------------->

1.2 **(6 points)** One way to narrowing down your selection is to *explore* the datasets. Use your knowledge of dplyr to find out at least *3* attributes about each of these datasets (an attribute is something such as number of rows, variables, class type...). The goal here is to have an idea of *what the data looks like*.

*Hint:* This is one of those times when you should think about the cleanliness of your analysis. I added a single code chunk for you below, but do you want to use more than one? Would you like to write more comments outside of the code chunk?

<!-------------------------- Start your work below ---------------------------->

> ### *EXPLORING DATASETS ATTRIBUTES*
>
> Datasets will be analized simunltaneous on the following order:\
> 1.apt_buildings 2.flow_sample 3.cancer_sample 4.vancouver_trees\
> \
> Fist, let's check the data format of the datasets


```r
class(apt_buildings)
```

```
## [1] "tbl_df"     "tbl"        "data.frame"
```

```r
class(flow_sample)
```

```
## [1] "tbl_df"     "tbl"        "data.frame"
```

```r
class(cancer_sample)
```

```
## [1] "spec_tbl_df" "tbl_df"      "tbl"         "data.frame"
```

```r
class(vancouver_trees)
```

```
## [1] "tbl_df"     "tbl"        "data.frame"
```

> \*\**All datasets are tibble*\
> \
> Checking dataset dimensions (Rows x columns)


```r
dim_desc(apt_buildings)
```

```
## [1] "[3,455 x 37]"
```

```r
dim_desc(flow_sample)
```

```
## [1] "[218 x 7]"
```

```r
dim_desc(cancer_sample)
```

```
## [1] "[569 x 32]"
```

```r
dim_desc(vancouver_trees)
```

```
## [1] "[146,611 x 20]"
```

> \*\**The smaller dataset with few columns and rows is flow_sample and the biggest is Vancouver_trees*\
> \
> Now, let's create a summary of dataset structure to check variables names and types.


```r
glimpse(apt_buildings)
```

```
## Rows: 3,455
## Columns: 37
## $ id                               <dbl> 10359, 10360, 10361, 10362, 10363, 10…
## $ air_conditioning                 <chr> "NONE", "NONE", "NONE", "NONE", "NONE…
## $ amenities                        <chr> "Outdoor rec facilities", "Outdoor po…
## $ balconies                        <chr> "YES", "YES", "YES", "YES", "NO", "NO…
## $ barrier_free_accessibilty_entr   <chr> "YES", "NO", "NO", "YES", "NO", "NO",…
## $ bike_parking                     <chr> "0 indoor parking spots and 10 outdoo…
## $ exterior_fire_escape             <chr> "NO", "NO", "NO", "YES", "NO", NA, "N…
## $ fire_alarm                       <chr> "YES", "YES", "YES", "YES", "YES", "Y…
## $ garbage_chutes                   <chr> "YES", "YES", "NO", "NO", "NO", "NO",…
## $ heating_type                     <chr> "HOT WATER", "HOT WATER", "HOT WATER"…
## $ intercom                         <chr> "YES", "YES", "YES", "YES", "YES", "Y…
## $ laundry_room                     <chr> "YES", "YES", "YES", "YES", "YES", "Y…
## $ locker_or_storage_room           <chr> "NO", "YES", "YES", "YES", "NO", "YES…
## $ no_of_elevators                  <dbl> 3, 3, 0, 1, 0, 0, 0, 2, 4, 2, 0, 2, 2…
## $ parking_type                     <chr> "Underground Garage , Garage accessib…
## $ pets_allowed                     <chr> "YES", "YES", "YES", "YES", "YES", "Y…
## $ prop_management_company_name     <chr> NA, "SCHICKEDANZ BROS. PROPERTIES", N…
## $ property_type                    <chr> "PRIVATE", "PRIVATE", "PRIVATE", "PRI…
## $ rsn                              <dbl> 4154812, 4154815, 4155295, 4155309, 4…
## $ separate_gas_meters              <chr> "NO", "NO", "NO", "NO", "NO", "NO", "…
## $ separate_hydro_meters            <chr> "YES", "YES", "YES", "YES", "YES", "Y…
## $ separate_water_meters            <chr> "NO", "NO", "NO", "NO", "NO", "NO", "…
## $ site_address                     <chr> "65  FOREST MANOR RD", "70  CLIPPER R…
## $ sprinkler_system                 <chr> "YES", "YES", "NO", "YES", "NO", "NO"…
## $ visitor_parking                  <chr> "PAID", "FREE", "UNAVAILABLE", "UNAVA…
## $ ward                             <chr> "17", "17", "03", "03", "02", "02", "…
## $ window_type                      <chr> "DOUBLE PANE", "DOUBLE PANE", "DOUBLE…
## $ year_built                       <dbl> 1967, 1970, 1927, 1959, 1943, 1952, 1…
## $ year_registered                  <dbl> 2017, 2017, 2017, 2017, 2017, NA, 201…
## $ no_of_storeys                    <dbl> 17, 14, 4, 5, 4, 4, 4, 7, 32, 4, 4, 7…
## $ emergency_power                  <chr> "NO", "YES", "NO", "NO", "NO", "NO", …
## $ `non-smoking_building`           <chr> "YES", "NO", "YES", "YES", "YES", "NO…
## $ no_of_units                      <dbl> 218, 206, 34, 42, 25, 34, 14, 105, 57…
## $ no_of_accessible_parking_spaces  <dbl> 8, 10, 20, 42, 12, 0, 5, 1, 1, 6, 12,…
## $ facilities_available             <chr> "Recycling bins", "Green Bin / Organi…
## $ cooling_room                     <chr> "NO", "NO", "NO", "NO", "NO", "NO", "…
## $ no_barrier_free_accessible_units <dbl> 2, 0, 0, 42, 0, NA, 14, 0, 0, 1, 25, …
```

```r
glimpse(flow_sample)
```

```
## Rows: 218
## Columns: 7
## $ station_id   <chr> "05BB001", "05BB001", "05BB001", "05BB001", "05BB001", "0…
## $ year         <dbl> 1909, 1910, 1911, 1912, 1913, 1914, 1915, 1916, 1917, 191…
## $ extreme_type <chr> "maximum", "maximum", "maximum", "maximum", "maximum", "m…
## $ month        <dbl> 7, 6, 6, 8, 6, 6, 6, 6, 6, 6, 6, 7, 6, 6, 6, 7, 5, 7, 6, …
## $ day          <dbl> 7, 12, 14, 25, 11, 18, 27, 20, 17, 15, 22, 3, 9, 5, 14, 5…
## $ flow         <dbl> 314, 230, 264, 174, 232, 214, 236, 309, 174, 345, 185, 24…
## $ sym          <chr> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, N…
```

```r
glimpse(cancer_sample)
```

```
## Rows: 569
## Columns: 32
## $ ID                      <dbl> 842302, 842517, 84300903, 84348301, 84358402, …
## $ diagnosis               <chr> "M", "M", "M", "M", "M", "M", "M", "M", "M", "…
## $ radius_mean             <dbl> 17.990, 20.570, 19.690, 11.420, 20.290, 12.450…
## $ texture_mean            <dbl> 10.38, 17.77, 21.25, 20.38, 14.34, 15.70, 19.9…
## $ perimeter_mean          <dbl> 122.80, 132.90, 130.00, 77.58, 135.10, 82.57, …
## $ area_mean               <dbl> 1001.0, 1326.0, 1203.0, 386.1, 1297.0, 477.1, …
## $ smoothness_mean         <dbl> 0.11840, 0.08474, 0.10960, 0.14250, 0.10030, 0…
## $ compactness_mean        <dbl> 0.27760, 0.07864, 0.15990, 0.28390, 0.13280, 0…
## $ concavity_mean          <dbl> 0.30010, 0.08690, 0.19740, 0.24140, 0.19800, 0…
## $ concave_points_mean     <dbl> 0.14710, 0.07017, 0.12790, 0.10520, 0.10430, 0…
## $ symmetry_mean           <dbl> 0.2419, 0.1812, 0.2069, 0.2597, 0.1809, 0.2087…
## $ fractal_dimension_mean  <dbl> 0.07871, 0.05667, 0.05999, 0.09744, 0.05883, 0…
## $ radius_se               <dbl> 1.0950, 0.5435, 0.7456, 0.4956, 0.7572, 0.3345…
## $ texture_se              <dbl> 0.9053, 0.7339, 0.7869, 1.1560, 0.7813, 0.8902…
## $ perimeter_se            <dbl> 8.589, 3.398, 4.585, 3.445, 5.438, 2.217, 3.18…
## $ area_se                 <dbl> 153.40, 74.08, 94.03, 27.23, 94.44, 27.19, 53.…
## $ smoothness_se           <dbl> 0.006399, 0.005225, 0.006150, 0.009110, 0.0114…
## $ compactness_se          <dbl> 0.049040, 0.013080, 0.040060, 0.074580, 0.0246…
## $ concavity_se            <dbl> 0.05373, 0.01860, 0.03832, 0.05661, 0.05688, 0…
## $ concave_points_se       <dbl> 0.015870, 0.013400, 0.020580, 0.018670, 0.0188…
## $ symmetry_se             <dbl> 0.03003, 0.01389, 0.02250, 0.05963, 0.01756, 0…
## $ fractal_dimension_se    <dbl> 0.006193, 0.003532, 0.004571, 0.009208, 0.0051…
## $ radius_worst            <dbl> 25.38, 24.99, 23.57, 14.91, 22.54, 15.47, 22.8…
## $ texture_worst           <dbl> 17.33, 23.41, 25.53, 26.50, 16.67, 23.75, 27.6…
## $ perimeter_worst         <dbl> 184.60, 158.80, 152.50, 98.87, 152.20, 103.40,…
## $ area_worst              <dbl> 2019.0, 1956.0, 1709.0, 567.7, 1575.0, 741.6, …
## $ smoothness_worst        <dbl> 0.1622, 0.1238, 0.1444, 0.2098, 0.1374, 0.1791…
## $ compactness_worst       <dbl> 0.6656, 0.1866, 0.4245, 0.8663, 0.2050, 0.5249…
## $ concavity_worst         <dbl> 0.71190, 0.24160, 0.45040, 0.68690, 0.40000, 0…
## $ concave_points_worst    <dbl> 0.26540, 0.18600, 0.24300, 0.25750, 0.16250, 0…
## $ symmetry_worst          <dbl> 0.4601, 0.2750, 0.3613, 0.6638, 0.2364, 0.3985…
## $ fractal_dimension_worst <dbl> 0.11890, 0.08902, 0.08758, 0.17300, 0.07678, 0…
```

```r
glimpse(vancouver_trees)
```

```
## Rows: 146,611
## Columns: 20
## $ tree_id            <dbl> 149556, 149563, 149579, 149590, 149604, 149616, 149…
## $ civic_number       <dbl> 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 7…
## $ std_street         <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
## $ genus_name         <chr> "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "…
## $ species_name       <chr> "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "C…
## $ cultivar_name      <chr> "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICL…
## $ common_name        <chr> "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBE…
## $ assigned           <chr> "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "…
## $ root_barrier       <chr> "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "…
## $ plant_area         <chr> "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "…
## $ on_street_block    <dbl> 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 7…
## $ on_street          <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
## $ neighbourhood_name <chr> "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "…
## $ street_side_name   <chr> "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD…
## $ height_range_id    <dbl> 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, …
## $ diameter           <dbl> 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00…
## $ curb               <chr> "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "…
## $ date_planted       <date> 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 19…
## $ longitude          <dbl> -123.1161, -123.1147, -123.0846, -123.0870, -123.08…
## $ latitude           <dbl> 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 4…
```

> \*\**While "apt_buildings" dataset variables are mostly characters, the "cancer_sample" dataset variables are all numeric, with exception of "diagnosis".*

<!----------------------------------------------------------------------------->

1.3 **(1 point)** Now that you've explored the 4 datasets that you were initially most interested in, let's narrow it down to 1. What lead you to choose this one? Briefly explain your choice below.

<!-------------------------- Start your work below ---------------------------->

>I will keep working with "vancouver_trees". I choose this dataset since there is a good balance between numeric and character variables. The dataset is not small, variables are easy to understand and it is interesting since I live in Vancouver.

<!----------------------------------------------------------------------------->

1.4 **(2 points)** Time for a final decision! Going back to the beginning, it's important to have an *end goal* in mind. For example, if I had chosen the `titanic` dataset for my project, I might've wanted to explore the relationship between survival and other variables. Try to think of 1 research question that you would want to answer with your dataset. Note it down below.

<!-------------------------- Start your work below ---------------------------->

>What is the overall height distribution of trees in Vancouver and in the neighborhoods ? Are there outlines with exceptionally tall heights and is it due tree age?

<!----------------------------------------------------------------------------->

# Important note

Read Tasks 2 and 3 *fully* before starting to complete either of them. Probably also a good point to grab a coffee to get ready for the fun part!

This project is semi-guided, but meant to be *independent*. For this reason, you will complete tasks 2 and 3 below (under the **START HERE** mark) as if you were writing your own exploratory data analysis report, and this guidance never existed! Feel free to add a brief introduction section to your project, format the document with markdown syntax as you deem appropriate, and structure the analysis as you deem appropriate. If you feel lost, you can find a sample data analysis [here](https://www.kaggle.com/headsortails/tidy-titarnic) to have a better idea. However, bear in mind that it is **just an example** and you will not be required to have that level of complexity in your project.

# Task 2: Exploring your dataset

If we rewind and go back to the learning objectives, you'll see that by the end of this deliverable, you should have formulated *4* research questions about your data that you may want to answer during your project. However, it may be handy to do some more exploration on your dataset of choice before creating these questions - by looking at the data, you may get more ideas. **Before you start this task, read all instructions carefully until you reach START HERE under Task 3**.

2.1 **(12 points)** Complete *4 out of the following 8 exercises* to dive deeper into your data. All datasets are different and therefore, not all of these tasks may make sense for your data - which is why you should only answer *4*.

Make sure that you're using dplyr and ggplot2 rather than base R for this task. Outside of this project, you may find that you prefer using base R functions for certain tasks, and that's just fine! But part of this project is for you to practice the tools we learned in class, which is dplyr and ggplot2.

1.  Plot the distribution of a numeric variable.
2.  Create a new variable based on other variables in your data (only if it makes sense)
3.  Investigate how many missing values there are per variable. Can you find a way to plot this?
4.  Explore the relationship between 2 variables in a plot.
5.  Filter observations in your data according to your own criteria. Think of what you'd like to explore - again, if this was the `titanic` dataset, I may want to narrow my search down to passengers born in a particular year...
6.  Use a boxplot to look at the frequency of different observations within a single variable. You can do this for more than one variable if you wish!
7.  Make a new tibble with a subset of your data, with variables and observations that you are interested in exploring.
8.  Use a density plot to explore any of your variables (that are suitable for this type of plot).

2.2 **(4 points)** For each of the 4 exercises that you complete, provide a *brief explanation* of why you chose that exercise in relation to your data (in other words, why does it make sense to do that?), and sufficient comments for a reader to understand your reasoning and code.

<!-------------------------- Start your work below ---------------------------->

>### To explore the research question

> To start, lets play with numbers and check the height distribution in Vancouver. Is there a trend for height ranges?


```r
#Use a density plot to explore any of your variables (task 2 - item 8).
#The dataset have a large number of rows and the "height_range_id" is in a scale from 0-10. Thus a easy way to identify a trend is using the distribution blot to visually analyze the height range.

trees_height <- ggplot(vancouver_trees, aes(height_range_id)) +
  geom_density()
plot(trees_height)
```

![image](https://github.com/stat545ubc-2023/mda-jmfvieira11/assets/65200070/8e3344be-19e2-451f-b0cb-3c0c58b87984)<!-- -->

> \*\* *The majority of the trees seem to be rated 1 or 2 in the range "height_range_id", with the highest peak for trees rated 2. Showing a preference for small and medium trees.*\
> \
> The previous plot shows a general distribution for the city. Is there a specific trend for height ranges in the neighborhoods?\
> Let's explore the relation between height range and neighborhood name.


```r
#Use a boxplot to look at the frequency of different observations within a single variable. (task 2 - item 6).
#The dataset have a large number of rows and several variables in "neighbourhood_name". Thus a good way to compare the variables is though visualization using bloxplot.

trees_height <- ggplot(vancouver_trees, aes(height_range_id, neighbourhood_name))+
  geom_boxplot()
plot(trees_height)
```

![image](https://github.com/stat545ubc-2023/mda-jmfvieira11/assets/65200070/7c533156-1ec2-4d33-a6b9-48fc86dcadb6)<!-- -->

> \*\* *None of the neighborhoods have a preference for higher height trees. Most neighborhoods have an average of trees ranked height 2, with exception of 5 neighborhoods (West Point Grey, West End, Shaughnessy, Kitsilano and Fairview) with an average of trees ranked height 3. It differs from the distribuition plot since it is not shown a preference for small height trees (height rank = 1)*
>
> \
> There are some neighborhoods holding trees with height range ranked 10. How many of these are there? Are these the same tree type? Is this related to the tree age?\
> To explore it, let's filter the dataset for trees ranked 10. To facilitate the visualization, I will group neighborhoods and then select to show only the interested variables.


```r
#Filter observations in your data according to your own criteria. (task 2 - item 5).
#Using the filter function is a easy way to select a specific variable as "height_range_id = 10". It also show number of rows, what indicate the number of events.

van_tall_tree <- vancouver_trees %>%
  filter(height_range_id == 10) %>%
  group_by(neighbourhood_name) %>%
  select(neighbourhood_name,genus_name,species_name,date_planted)
print(van_tall_tree)
```

```
## # A tibble: 12 × 4
## # Groups:   neighbourhood_name [9]
##    neighbourhood_name       genus_name  species_name date_planted
##    <chr>                    <chr>       <chr>        <date>      
##  1 KITSILANO                ULMUS       AMERICANA    NA          
##  2 KITSILANO                ULMUS       AMERICANA    NA          
##  3 MARPOLE                  ROBINIA     PSEUDOACACIA 1998-01-06  
##  4 KENSINGTON-CEDAR COTTAGE QUERCUS     RUBRA        NA          
##  5 KENSINGTON-CEDAR COTTAGE QUERCUS     RUBRA        NA          
##  6 KERRISDALE               THUJA       PLICATA      NA          
##  7 SHAUGHNESSY              ACER        PALMATUM     NA          
##  8 RENFREW-COLLINGWOOD      PSEUDOTSUGA MENZIESII    NA          
##  9 RILEY PARK               PSEUDOTSUGA MENZIESII    NA          
## 10 DUNBAR-SOUTHLANDS        PSEUDOTSUGA MENZIESII    NA          
## 11 DUNBAR-SOUTHLANDS        ABIES       SPECIES      NA          
## 12 ARBUTUS-RIDGE            POPULUS     TRICHOCARPA  NA
```

> \*\* *There are only twelve trees ranked height 10 in the dataset. Interestingly, when more than one tree in the same neighborhood, there are the same species. The variables does not have information about the date planted, with exception of one. Thus is not possible to correlate the height rank and the age of the three.*
>
> \
> Since it was not possible to explore the tree age with the previous analysis, I select the only tree species that have information about the date planted (*ROBINIA PSEUDOACACIA*) as a tree to explore further. Is this tree naturally higher? Is it height related to its age? Is there this species in other neighborhoods?\
> To explore it, I will filter vancouver_trees dataset to generate a new tible containing only the *ROBINIA PSEUDOACACIA* tree species. Then i will explore the relationship between the tree age (date planted) and the neighborhood. To facilitate comparison with the previous data I will color it to indicate the tree height rank.


```r
###Make a new tibble with a subset of your data, with variables and observations that you are interested in exploring. (task 2 - item 7).
#In this case, it is easy to make a new tibble to use as basis for a new plot than using several tools to filter the variable of interest.

#new tibble = van_RobPseucacia
van_RobPseucacia <- vancouver_trees %>%
  filter(genus_name == "ROBINIA", species_name == "PSEUDOACACIA")

#plot to explore variables relationship
RobPseucacia_neighbs <- ggplot(van_RobPseucacia, aes(date_planted, neighbourhood_name, colour =height_range_id)) +
  geom_point()
plot(RobPseucacia_neighbs)
```

```
## Warning: Removed 295 rows containing missing values (`geom_point()`).
```

![image](https://github.com/stat545ubc-2023/mda-jmfvieira11/assets/65200070/982faa37-47f6-400b-a220-f3a466c11a53)<!-- -->

> \*\* *There is not a clear relation between date planted and height rank for the ROBINIA PSEUDOACACIA tree species, thus the high height rank is not due the tree age. Some trees were planted before 1995 and range below 2.5 while some were planted after 2005 and range above 5. Fairview is the only neighborhood without this tree species, and there is no a clear preference across neighborhoods.*
>
> Overall, based on the trends and patterns on height range of trees in Vancouver, it was possible to see a preference for trees leaning to small or medium over taller trees.\
> When narrowing down into the neighborhood, it's possible to reinforce the non-preference for higher tree sizes and a preference for medium tree heights. There is some outliners with some especially tall trees, and exploring one of them (*ROBINIA PSEUDOACACIA*), is possible to observe that there's no relation between their height and age (date planted) or any neighborhood pattern preference.\
>
> <!----------------------------------------------------------------------------->

# Task 3: Choose research questions

**(4 points)** So far, you have chosen a dataset and gotten familiar with it through exploring the data. You have also brainstormed one research question that interested you (Task 1.4). Now it's time to pick 4 research questions that you would like to explore in Milestone 2! Write the 4 questions and any additional comments below.

<!--- *****START HERE***** --->

> ### Choosing 4 research questions to further explore the dataset.
> 
> To continue my investigation about Vancouver and its neighborhoods preferences about tree height and types I will explore the following questions:
> 
> 1.  What are the most common tree species in the neighborhoods?
> 2.  How does tree height vary among different tree species? Are certain species generally taller than others?
> 3.  Are there temporal trends in tree height? Has there been a change in the height of trees planted over the years?
> 4.  Do some trees in specific neighborhoods tend to grow taller?

<!----------------------------->

# Overall reproducibility/Cleanliness/Coherence Checklist

## Coherence (0.5 points)

The document should read sensibly from top to bottom, with no major continuity errors. An example of a major continuity error is having a data set listed for Task 3 that is not part of one of the data sets listed in Task 1.

## Error-free code (3 points)

For full marks, all code in the document should run without error. 1 point deduction if most code runs without error, and 2 points deduction if more than 50% of the code throws an error.

## Main README (1 point)

There should be a file named `README.md` at the top level of your repository. Its contents should automatically appear when you visit the repository on GitHub.

Minimum contents of the README file:

-   In a sentence or two, explains what this repository is, so that future-you or someone else stumbling on your repository can be oriented to the repository.
-   In a sentence or two (or more??), briefly explains how to engage with the repository. You can assume the person reading knows the material from STAT 545A. Basically, if a visitor to your repository wants to explore your project, what should they know?

Once you get in the habit of making README files, and seeing more README files in other projects, you'll wonder how you ever got by without them! They are tremendously helpful.

## Output (1 point)

All output is readable, recent and relevant:

-   All Rmd files have been `knit`ted to their output md files.
-   All knitted md files are viewable without errors on Github. Examples of errors: Missing plots, "Sorry about that, but we can't show files that are this big right now" messages, error messages from broken R code
-   All of these output files are up-to-date -- that is, they haven't fallen behind after the source (Rmd) files have been updated.
-   There should be no relic output files. For example, if you were knitting an Rmd to html, but then changed the output to be only a markdown file, then the html file is a relic and should be deleted.

(0.5 point deduction if any of the above criteria are not met. 1 point deduction if most or all of the above criteria are not met.)

Our recommendation: right before submission, delete all output files, and re-knit each milestone's Rmd file, so that everything is up to date and relevant. Then, after your final commit and push to Github, CHECK on Github to make sure that everything looks the way you intended!

## Tagged release (0.5 points)

You've tagged a release for Milestone 1.

### Attribution

Thanks to Icíar Fernández Boyano for mostly putting this together, and Vincenzo Coia for launching.
