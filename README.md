# Covid_19 Analysis

## Table of Contents
*[project Overview](#project-overview)
*[Data Sources](#data-sources)
*[Tools](#tools)
*[Data Cleaning/prep](#data-cleaning/prep)
*[Exploratory Data Analysis](#exploratory-data-analysis)
*[Data Analysis](#data-analysis)
*[Results/Findings](#results/findings)
*[Recommendation](#recommendation)

## Project Overview

A new coronavirus designated 2019-nCoV was first identified in Wuhan, the capital of China's Hubei province. People developeed pneumonia without a clear cause and for which existing vaccines or treatments were not effective. The virus has shown evidence of human-to-human transmission. Transmission rate (rate of infection) appeared to escalate in mid January 2020. As of 30 January 2020, approximately 8,243 cases have been confirmed.
 
### Data Sources

The primary dataset used foer this analysis was gotten from Google

### Tasks

This dataset was downlaoded and uploaded into Power BI, where we started by transforming it using power query editor, we corrected the data types of some of the fields, irrelevant columns were removed, the dataset was completely cleaned before we begin DAX calculations and creating of Measures to help us get the appropriate values as required. 
Afterwhich, we went on to load the clean dataset into Power BI dashboard, where visualizations started.

### Tools
-Power BI(for both cleaning and report creation) [Download here](https://www.microsoft.com/en-us/power-platform/products/power-bi/desktop)

### Data Cleaning/Prep

* Data loading into power query editor
* carrying out some DAX expressions
* Creating of tables for additional columns
* Creating of measures

### Exploratory Data Analysis

 * What age group took the vaccine
 * What population had a status (either boosted or vaccinated)
 * What year had the most cases
 * Comparism between people hospitalized and death
 * Number of deaths among those that are unvaccinated, vaccinated or boosted


 ### Data Analysis

 ```PowerBI
Vaccination Coverage = DIVIDE([Population Vaccinated] + [Population Boosted],[Total Population])
Total Cases = SUM('COVID-19_Outcomes'[Cases])
Total Deaths = SUM('COVID-19_Outcomes'[Deaths])
Total Hospitalization = SUM('COVID-19_Outcomes'[Hospitalizations])
Total Population = 'COVID-19_Outcomes'[Population Boosted] + 'COVID-19_Outcomes'[Population Unvaccinated] + 'COVID-19_Outcomes'[Population Vaccinated]
Case Rate Vaccinated = SUM('COVID-19_Outcomes'[Vaccinated Rate])
Case Rate Unvaccinated = SUM('COVID-19_Outcomes'[Unvaccinated Rate])
Average cases rate by age group = AVERAGE('COVID-19_Outcomes'[Cases])```


### Results/Findings

The Analysis results are summarized as follows:

* More deaths occured from the unvaccinated people
* Ages 50-64 had more of the unvaccinated group, while ages 80 and above had more of the vaccinated group
* More people collected boosted vaccine more than the complete vaccination and unvaccination

### Recommendation

* My recommendation is that more people should be made to take the vaccine, or at least a boosted version, but never left unvaccinated.

### Limitations

* I had to set all the null values under death, hospitalization and cases to zero because removing them from the dataset will affect other columns which will make the analysis imcomplete.
* Also, some columns such as Age adjusted vaccination rate and ratio, and Age adjusted boosted rate and ratio where removed due to much empty cells, and its irrelevant
