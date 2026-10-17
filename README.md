# Biodiversity in National Parks

## 1. Project Overview

This project investigates patterns in conservation status across species categories and explores differences in recorded species observations across national parks

Using python, the project applies data cleaning, exploratory data analysis, data visulaisation and statisitcal analysis to investigate biodiversity-related patterns in the supplied datasets.

## 2. Research Questions 

The analysis aims to answer to following questions: 

- How does recorded conservation status vary across species categories ? 
- Is there an association between species category and recorded conservation status ? 
- How do recorded species observations vary across national parks ? 
- Which species categories account for the highest observation counts in each park ? 

## 3. Datasets 

The project uses two CSV datasets: 

- species_info.csv: contains species information, including scientifc names, common names, species categories and conservation status.
- obervations.csv - contains recorded species observations counts across national parks. 

## 4. Tools and Technologies

- Python 
- Pandas 
- Seaborn 
- Matplotlib
- SciPy
- Jupyter Notebook 
- Github

## 5. Project Methodology 

The project follows these stages: 
    
    1. Load and inspect the data.
    2. Investigate missing values and duplicate records.
    3. Clean and prepare the data.
    4. Conduct exploratory data analysis. 
    5. Create visualisations to communicate findings. 
    6. Apply statstical tests where appropriate. 
    7. Interpret the results and identify limitations. 
    8. Summarise the key findings and conclusions.

## 6. Data Cleaning and Preparation

### Missing Values 

The conservation_status column in species_info.csv contains 5,633 missing values out of 5,824 records, representing approximately 96.7% of the dataset. 

Missing values have been investigated by species category and visualised using a bar chart of the percentage missing within each category. 

The missing values have been preserved during the initial investigation rather than automatically replacing them with a conservation status label. Their treatment will be determined according to the requirements of the subsequent analysis. 

### Duplicate Records

An initial duplicate check is identified: 

- species_info.csv: 0 duplicate rows.
- observations.csv: 15 duplicate rows. 

The 15 exact duplicate rows were removed from the observations dataset using pandas drop_duplicates() method. The dataset was then checked again to verify that no exact duplicate rows remained. 

## 7. Exploratory Data Analysis 

### Initial Dataset Inspection

The species dataset contains 5,824 rows and four columns, while the observations dataset contains 23,281 rows and three columns following duplicate removal.

The species dataset has missing values only in the `conservation_status` column. The observations dataset contains no missing values in its three columns. The `observations` column is stored as an integer, allowing numerical analysis of recorded observation counts.

Both datasets have the expected basic structure for further exploratory analysis. The uniqueness of species identifiers and the relationship between the datasets will be checked before merging.

### Distribution of Species Categories

Vascular plants account for 76.75% of the 5,824 species records, making them the dominant category in the dataset. Birds represent the second-largest category at 8.95%, while all remaining categories individually account for less than 6%.

This uneven distribution is important when interpreting subsequent analyses, as overall results may be strongly influenced by the high representation of vascular plants. Species counts and observation counts will therefore be examined separately.


### Distribution of Recorded Conservation Status

Of the 191 species with a recorded conservation status, 161 (84.29%) are classified as Species of Concern. A further 16 are Endangered, 10 are Threatened and four are In Recovery.

The distribution is heavily concentrated in the Species of Concern category. However, these results describe only species with a recorded conservation status and should not be generalised to all species in the dataset, given the high proportion of missing values.

### Conservation Status by Species Category

The distribution of recorded conservation statuses varies across species categories. Fish and amphibians have relatively high proportions of records classified as Endangered or Threatened, while the recorded statuses for nonvascular plants and reptiles fall entirely within the Species of Concern category.

A continegency table and a stacked bar chart were used to compare recorded conservation statuses across categories. 

However, the percentages are calculated only from species with a recorded conservation status. The number of recorded statuses also varies between categories, so these results should be interpreted cautiously and do not establish the conservation risk of every species within a category.

### Distribution of Observations Across National Parks

The obervations dataset was grouped by national park to calculate the total number of recorded observations for each park. The percentage share of total recorded observations was then calculated and visualised using a bar chart.

The distribution of recorded obervations was: 

- Yellowstone National Park: 43.54%
- Yosemite National Park: 26.05% 
- Bryce National Park: 17.39% 
- Great Smoky Mountains National Park: 13.02% 

Together, Yellowstone and Yosemite account for approximately 70% of recorded observations. 

These differences describe the distribution of observation counts in the dataset and should not be interpreted as direct measure of wildlife abundance or biodivesity. 

### Observation Counts by Species Category and National Park

A pivot table was created to aggregate recorded observation counts by species category across the four national parks. This allowed comparisons of observations patterns between parks and categories. 

The results showed that vascular plants had the highests recroded observation counts in every park, followed by birds and nonvascular plants. Yellowstone National Park had the highest observation count across every species category.

To account for differences in total observation counts between national parks, the percentage of observations represented by each species category was calculated for each park.

The percentage distribtuons were similar across all four parks. Vascular plants accounted for approximately 76.5-76.8% of recorded observations in each park, while birds represented around 9%. The remaining species categories also showed relatively small differences in their proportions between parks.

These findings suggets that, despite differences in the total number of recorded observations, the relative distribution of observations across species categories is consistent across all four parks. 

## 8. Statistical Analysis

### Chi-Square Test of Independence

A chi-sqaure test of independence was used to investigate wheather there was an association between species category and recorded conservation status. 

#### Hypotheses

 - Null hypothesis: Species cateogry and recorded conservation status are independent.
 - Alternative hypothesis: There is an association between species categories and recorded conservation status. 

 #### Test results

 The original contingency table produced the following results:

 - Chi-square statistic: 53.92
 - p-value: 0.0000189
 - Degrees of freedom: 18 

 However, checking the expected frequencies revealed that 22 cells had expected counts below 5, including 14 cells with expected counts below 1. This indicated that the assumptions required for a reliable chi-square statistic approximation were not satsified. 

As a resukt of this, we cannot use this to reliably come to a conclusion on if there is an association between the category of species and the conservation status of animals. 

## 9. Key Findings 

### Variation in Recorded Status Across Species Categories

The analysis compared the distribution of recorded conservation statuses across species categories using a contingency table and a 100% stacked bar chart.

Species of Concern was the most frequently recorded status overall, accounting for 161 of the 191 records with a recorded conservation status (84.29%). However, the distribution varied between categories:

- Birds: Species of Concern accounted for 91.14% of recorded statuses, with In Recovery accounting for 3.80%.
- Mammals: Species of Concern represented 73.68% of recorded statuses, while 18.42% were Endangered.
- Fish: Recorded statuses were more evenly distributed, with 36.36% classified as Species of Concern, 36.36% as Threatened and 27.27% as Endangered.
- Amphibians: Species of Concern accounted for 57.14% of recorded statuses, while 28.57% were Threatened.
- Nonvascular plants and reptiles: All recorded conservation statuses were classified as Species of Concern.
- Vascular plants: Species of Concern accounted for 93.48% of recorded statuses.

These findings show that the distribution of recorded conservation statuses differs across species categories. However, the percentages describe only records with a recorded status, not the proportion of all species within each category that face conservation concerns. Since 96.7% of the species records had missing conservation-status information, the findings should be interpreted cautiously.

### Association Between Species Category and Recorded Conservation Status

A chi-square test of independence was conducted to investigate wheather species category was associated with recorded conservation status. However, the expected-count assumptions were not satisfied. Therefore, the test results couldn't be treated as conclusive, and no statistical association could be concluded between the species category and conservation status variables.

### Recorded Species Observations Across National Parks

Yellowstone National Park accounted for the largest share of recorded observations (43.54%), followed by Yosemite (26.05%), Bryce (17.39%) and Great Smoky Mountains (13.02%). These figures show that recorded observations counts differed across the four parks. However, they do not necessarily refect differences in actual wildlife abundance or biodiversity, as observation counts may also be affected by survey effort and recording practices.

### Species Categories With the Highest Observation Counts in Each Park

The park-by-category pivot table showed that vascular plants had the highest recorded observation counts in each of the four national parks, followed by birds and nonvascular plants. Yellowstone had the highest recorded counts across the species categories examined.

When observation counts were converted into percentages within each park, the category distributions were very similar. Vascular plants accounted for approximately 76.5–76.8% of recorded observations in each park, suggesting that the overall composition of recorded observations was consistent across the four parks.

### Overall Summary 

The analysis identified differences in recorded observation counts between national parks, while the proportional distribution of observations across species categories remained relatively consistent. Species of Concern was the most frequently recorded conservation status, but substantial missing information limited the interpretation of conservation-status patterns. The chi-square analysis could not provide a definitive statistical conclusion because its expected-count assumptions were not satisfied.

## 10. Limitations 

### Missing Conservation Status information

A major limitation of the dataset was the high proportion of missing conservation-status values. Of the 5,824 records in the species dataset, 5,633 (96.7%) had no recorded conservation status. As a result, the analysis of conservation status was based on only 191 records. These missing values were not automatically classified as species with no conservation concerns, as the absence of a recorded status does not necessarily indicate that a species has no conservation concerns. This limits the extent to which the findings can be generalised across all species categories.

### Limitations of the Chi-Square Analysis 

Chi-square tests of independence were used to investigate a potential association between species category and recorded conservation status. However, both the original and grouped contingency tables contained expected counts below the usual recommended thresholds. This meant that the assumptions required for a reliable chi-square approximation were not satisfied. Consequently, the resulting p-values were not treated as definitive statistical evidence of an association. The analysis instead focused on descriptive patterns in the contingency tables and visualisations.










