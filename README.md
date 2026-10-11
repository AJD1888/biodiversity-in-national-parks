# Biodiversity in National Parks

## 1. Project Overview

This project investigates patterns in conservation status across species categories and explores differences in recorded species observations across national parks

Using python, the project applies data cleaning, exploratory data analysis, data visulaisation and statisitcal analysis to investigate biodiversity-related patterns in the supplied datasets.

## 2. Research Questions 

The analysis aims to answer to following questions: 

- How does recorded conservation status vary across species categories ? 
- Is there an assocition between species category and recorded conservation status ? 
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

However, the percentages are calculated only from species with a recorded conservation status. The number of recorded statuses also varies between categories, so these results should be interpreted cautiously and do not establish the conservation risk of every species within a category.

### Distribution of Observations Across National Parks

Yellowstone National Park accounts for 43.54% of all recorded observations, followed by Yosemite National Park at 26.05%. Bryce National Park contributes 17.39%, while Great Smoky Mountains National Park accounts for 13.02%.

Together, Yellowstone and Yosemite account for approximately 69.59% of recorded observations. These differences describe the distribution of observation counts in the dataset and should not be interpreted as direct measures of wildlife abundance or biodiversity.

## 8. Statistical Analysis

## 9. Key Findings 

## 10. Limitations 








