# CDC NORS Outbreak Analysis

## Problem Statement

The CDC National Outbreak Reporting System (NORS) contains reported foodborne, waterborne, and related disease outbreaks across the United States. In the dataset covering 1971–2023, for 24,889 outbreaks, Norovirus accounted for 52.75% (13,129) of reported outbreaks, compared with 15.50% (3,857) for Salmonella. However, differences in outbreak frequency alone do not provide a complete understanding of the public-health burden. Examining how different etiologies vary in transmission modes, outbreak settings, outbreak size, hospitalization, and mortality can help identify important patterns that may inform public-health measures, infection-control practices, and food-safety interventions.

---

## Executive Summary

This project used CDC NORS data from 1971–2023 to explore patterns across reported disease outbreaks. The dataset was cleaned by retaining outbreaks with a single confirmed etiology and excluding missing, suspected, and multiple-etiology records. Etiologies were standardized and the ten most frequent were retained individually, with the remainder grouped as `Other`.

The analysis was descriptive and exploratory, using Python, Pandas, and visualization libraries. Counts, proportions, grouped summaries, heatmaps, bar charts, and boxplots were used to examine outbreak patterns. No predictive models were used.

Norovirus was the most frequently reported etiology, accounting for **52.75%** of outbreaks, followed by Salmonella at **15.50%**. Etiologies showed distinct seasonal, transmission, and setting patterns. Norovirus was strongly associated with person-to-person transmission and winter outbreaks, while Salmonella showed greater foodborne and warmer-season activity. Legionella pneumophila had the highest proportions of outbreaks with recorded hospitalization (**83.6%**) and death (**27.6%**).

---

## File Directory

| File                                 | Description                                 |
| ------------------------------------ | ------------------------------------------- |
| `README.md`                          | Project documentation                       |
| `Code_Folder`                        | Data cleaning and analysis                  |
| `Data_Folder`                        | Raw and Cleaned dataset                     |
| `Presentation_Folder`                | Project presentation and visualisations                    |

---

## Data and Data Dictionary

**Source:** CDC National Outbreak Reporting System (NORS)

https://data.cdc.gov/Foodborne-Waterborne-and-Related-Diseases/NORS/5xkq-dg7x

The dataset contains reported foodborne, waterborne, and related disease outbreaks in the United States.

### Dictionary
| Feature                        | Description                                                                |
| ------------------------------ | -------------------------------------------------------------------------- |
| `Year`                         | Year of the earliest reported illness onset                                |
| `Month`                        | Month of the earliest reported illness onset                               |
| `State`                        | State where exposure occurred; may include multistate outbreaks            |
| `Primary Mode`                 | Primary mode of transmission                                               |
| `Etiology`                     | Reported genus/species or other identified cause of the outbreak           |
| `Serotype or Genotype`         | Reported serotype or genotype                                              |
| `Etiology Status`              | Whether the reported etiology was confirmed or suspected                   |
| `Setting`                      | Setting where exposure occurred                                            |
| `Illnesses`                    | Estimated number of primary cases in the outbreak                          |
| `Hospitalizations`             | Number of primary cases hospitalized                                       |
| `Info On Hospitalizations`     | Number of primary cases for whom hospitalization information was available |
| `Deaths`                       | Number of primary cases who died                                           |
| `Info On Deaths`               | Number of primary cases for whom survival information was available        |
| `Food Vehicle`                 | Implicated food for foodborne outbreaks                                    |
| `Food Contaminated Ingredient` | Contaminated ingredient for foodborne outbreaks                            |
| `IFSAC Category`                   | For foodborne outbreaks only, the IFSAC food category of the contaminated ingredient                                           |
| `Water Exposure`               | For waterborne outbreaks only, the implicated type of water exposure.        |
| `Water Type`                 | For waterborne outbreaks only, a description of the venue, water system or device/structure that was the vehicle for waterborne exposure to microbial pathogens, chemicals, or toxins.                                    |
| `Animal Type` | For animal contact outbreaks only, the type of animal involved                            |

### Cleaned Dataset Features
The final analytical dataset was restricted to:
* Outbreaks with a recorded etiology
* A single reported etiology
* A confirmed etiology
* Records from 1971–2023

Additional transformations included:
* Standardizing selected etiology classifications
* Selecting the ten most frequently reported etiologies
* Combining remaining etiologies into `Other`
* Grouping detailed outbreak settings into broader setting categories

| Feature                | Description                                                                                 |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| `etiology_list`        | Temporary list created by splitting multiple etiology entries                               |
| `etiology_status_list` | Temporary list created by splitting multiple etiology-status entries                        |
| `Etiology_clean`       | Standardized etiology classification used for analysis                                      |
| `Etiology_top`         | Ten most frequent etiologies retained individually; remaining etiologies grouped as `Other` |
| `Setting_group`        | Broader setting categories created from the original detailed setting variable              |
> `etiology_list` and `etiology_status_list` were intermediate cleaning variables rather than analytical variables.
---

## Key Findings
* **Norovirus** accounted for 52.75% of outbreaks.
* **Salmonella** accounted for 15.50%.
* Norovirus showed a strong **winter** pattern and was associated with person-to-person transmission.
* Salmonella showed greater **foodborne and warmer-season** activity.
* Outbreak settings differed substantially by etiology.
* Median outbreak size was **16 illnesses overall**, with Norovirus at 25 and Salmonella at 9.
* **Legionella pneumophila** had the highest proportion of outbreaks with recorded hospitalization and death.
---

## Conclusions & Recommendations
Outbreak frequency alone does not capture the full public-health significance of an etiology. Different etiologies showed distinct patterns in transmission, setting, outbreak size, hospitalization, and mortality.

Public-health surveillance should therefore consider both **how frequently an etiology occurs and the characteristics and outcomes associated with its outbreaks**.

---

## Further Research
Future analysis could investigate:
* Etiology-specific seasonal mechanisms
* Salmonella trends by serotype
* Relationships between transmission mode and setting
* Statistical or predictive modelling of outbreak outcomes

---

## Limitations
* NORS contains **reported**, not necessarily all, outbreaks.
* Reporting practices changed over the study period.
* Restricting the dataset to single confirmed etiologies excludes some outbreaks.
* `Other` combines diverse etiologies.
* This analysis identifies associations and patterns, not causation.

---

## Acknowledgement
This project uses publicly available data from the **U.S. Centers for Disease Control and Prevention (CDC) National Outbreak Reporting System (NORS)**.
The analysis, data cleaning, feature engineering, exploratory analysis, and visualizations were conducted using Python and Pandas.
