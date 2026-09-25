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

## Research Questions 

1. What is the distribtution of conservation status over different animals ? 

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
