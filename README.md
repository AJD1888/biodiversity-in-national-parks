# Biodveristy in national parks project 

## Project Overview

The main goal of the project is to investigate wheather there are patterns between speicies type and conservation status, while also exploring how species observations vary between national parks 

## Objectives 

- Explore the sepcies and obvervations data sets.
- Clean both datasets so they are ready to be analysed.
- Investigate the distribution of conservation statuses.
- Compare conservation statuses accross different species categories.
- Investigate wheather species category and conservation status are realated. 
- Analyse species observations across different national parks.
- Create visualisations to communicate key findings. 
- Summarise findings and identify limitations in the data.

## Data 

The project uses two datasets: 

- 'species_info.csv'
- 'observations.csv'

## Tools 

- Python
- Pandas 
- NumPy 
- Matplotlib 
- Seaborn 
- Jupyter Notebook 
- Github 

## Methodology 

The analysis will follow the process: 

1. Load the datasets
2. Expolore and understand the data 
3. Clean and prepare the data 
4. Perform exploratory analysis 
5. Conduct statsitcal analysis where appropriate 
6. Create visualisations 
7. Interpret the findings 
8. Summarise conclusions and limitations. 


## Analysis report

### Clean and prepare the data

Initially, the two csv files, 'species_info.csv' and 'observations.csv' were loaded into two data frames, 'species_info_df' and 
'observations_df' respectively for inspection. Upon exploring the data it was found that the observations dataframe had 15 duplicate values and the species info dataframe had 5633 missing values in the conservation status column. To deal with the duplicate data in the observations dataframe, the drop_duplicates() function was used. Following on from this, the NaN values in the conservation status were filled with the value 'No concern' using the .fillna() function. This was done because having this many species without a conservation status having no values could skew later analysis on the biodiversity in the parks as analytical functions may exclude these rows as a result of the missing values. Moreover, the missingness in the column is structured, suggesting that none of the other values for other rows in this column apply to these species, which leaves only one option and that is for them not to be endangered.  


### Exploratory Data Analysis 

To start exploring our data, wanted to look at the distribution of conservation status over different types of animal. A contiengency table of the category and conservation_status columns was created and converted to percentages for use in a bar chart. A stacked bar chart was them plotted to show how the different conservation status varied for each category of animal. However, this did not paint a clear picture so the conversation status column had to be simplified. A new column 'is_protected' was creating, storing FALSE for rows that contained 'No concern' in the conservation status column and TRUE otherwise. 

From here, the same process of creating a contingency table was then followed but this time for the category and is_protected columns. Another stacked bar chart was plotted, this time showing the split of animals that were protected and not prodtected as a percentage for each category. 

Looking at the observations data frame, firstly the sum of all observations and mean observations were calculated. The observations per park was then caculated and converted into percentages, allowing us to visualise a pie chart showing the percentage of observations that occured overall in each park. From this, we can see taht the majority of obervations ocurred at yellowstone national park (43.5%), with the next closest percentage of total observations being at Yosemite National Park (26.0%).

Both data frames were then merged to look at the most dominant category of animal per park. The dataframe was goruped by park name and category, and fron there the obervations were summed. This allowed us to get the maximum observation in each park. This analysis concluded that across all parks the 'Vascular Plant' was the most popular category of species observed. 

### Statistical Analysis

Following on from EDA, statistical analysis was then performed to find out if there is any association between the category of animal and coservation status. The contingency table from earlier was taken and put into the chi2_contingency() function, giving us a value for the chi-sqaure statistic and the expected contingency tabke. Initally, the expected contigency table produced very large numbers so this was converted to a data frame for easier inspection. A chi-square value of 469.5 was returned, revealing a statistically significant relationship between species cateogry and protection status. 

Comparing actual counts against expected values demonstrates that Mammals (38 observed vs 7.02 expected) and Birds (79 observed vs 17.09 expected) are protected at substantially higher rates than expected. Conversley, Vascular Plants are protected at a significantly lower rate than expected (46 observed vs 146.60 expected)



