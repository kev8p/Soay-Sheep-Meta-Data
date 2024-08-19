# Soay-Sheep-Meta-Data

## Overview
This document provides an overview of the Male_Lambs data processing script, authored by Kevin Dang on June 7, 2024. The script is designed to process and analyze data related to male lambs, focusing on various aspects such as horn length, survival rates, and fecundity. The analysis is conducted using R Markdown and generates an HTML document output.

## Prerequisites
To run the script, you will need R (version 4.0 or higher is recommended) and several R packages, including ggplot2 and dplyr.

# Data Preparation and Processing
## Data Files
The script requires the following CSV files to be available in the specified data directory:

Fecundity.csv: Contains data related to lamb fecundity.
Birth_Data.csv: Provides information on the birth and death dates of lambs.
Horn_Data.csv: Includes measurements of horn lengths.
Population_Data.csv: Contains data on population density.

 
Script Breakdown
The script begins by loading the required data files and setting the working directory to the location of these files. It then merges and formats the data, focusing specifically on male lambs with normal horn morphologies. The data is filtered to include only records from 1986 to 2021, and irrelevant or duplicate entries are removed. Additionally, date fields are formatted for further processing.

To ensure the accuracy of the data, a random sample is examined to verify that the processing steps have produced logical results. The script then calculates environmental quality based on lamb survival rates. This involves aggregating the number of lambs born each year and assessing their survival rates, which are then classified into categories of environmental quality.

Further spot checks are performed to confirm that the survival calculations are logical. The script calculates survival rates for each year and categorizes them into quantiles to assess environmental quality. This information is then merged with the original dataset to provide a comprehensive view of each lamb’s environmental context.

Visualization is a key part of the analysis. The script generates histograms to display the distribution of survival rates and lamb densities, and it creates bar plots and box plots to visualize the distribution of environmental quality and horn measurements. These visualizations help to understand the data better and assess any significant differences in horn length across different environmental conditions.

#  Data Analysis
## Introduction
This analysis investigates the impact of horn length on the survival and fecundity of Soay sheep. We use data on male lambs to assess how horn length influences first-year survival and breeding success, considering environmental quality and population density. The analysis involves fitting generalized linear mixed models (GLMMs) to examine the effects of horn length and other variables on the outcomes of interest.

## Data Preparation
The dataset, data2.csv, is loaded and prepared for analysis. Horn length is standardized to ensure comparability across models. Environmental quality is categorized into four levels: "Very-Poor," "Poor," "Good," and "Very-Good." These factors are incorporated into the models to evaluate their interactions with horn length.

## Models for First Year Survival
Model Structures
We assess the effect of horn length on the probability of first-year survival using three models:

Model 1: Includes horn length, environmental quality, and their interaction, with random intercepts for the year of birth (YoB).
Model 2: Assesses horn length with a random slope for YoB, excluding the interaction term.
Model 3: Considers horn length, scaled village density, and their interaction, with random intercepts for YoB.
Results and Interpretation
Model 3, which includes village density, is summarized with significant findings indicating that the effect of horn length on survival probability varies significantly across years of birth. The low p-value (p < 0.001) in the model comparison suggests that horn length impacts first-year survival differently depending on the birth year.

## Plots

Plot 1.1 displays the effects of horn length on survival probability by environmental quality. Bar plots with error bars illustrate how the influence of horn length on survival varies with environmental conditions.

Plot 1.2 examines the random regression coefficients, showing the variation in horn length effects on survival across different years. A line plot visualizes the fluctuations in these effects, highlighting the impact of horn length on survival probability year by year.

Plot 1.3 examines how the the effect of horn length on survival probability changes at different densities based on the interaction 

## Models for First Year Fecundity
Fecundity Analysis
The fecundity models analyze the probability of a male lamb breeding successfully in its first year, based on horn length and environmental factors.

Model 1: Examines the interaction between horn length and environmental quality.
Model 2: Uses random slopes for horn length across years of birth.
Model 3: Includes village density and its interaction with horn length.
Results and Interpretation
The random slope model for fecundity shows variability in how horn length influences breeding success across years. However, the significance tests suggest that the variation in fecundity due to horn length is not as pronounced as for survival. The p-values for fecundity indicate no significant fluctuating selection based on horn length.

## Plots
Plot 2.1 presents the effects of horn length on breeding success by environmental quality. Similar to survival, bar plots with error bars illustrate how environmental conditions modify the relationship between horn length and fecundity.

Plot 2.2 shows the random regression coefficients for fecundity, plotting how the effect of horn length on breeding success varies across years. This plot helps visualize the year-to-year fluctuations in fecundity related to horn length.

#Plot 2.3 examines how the the effect of horn length on breeding success probability changes at different densities based on the interaction 

## Conclusion
The analysis reveals that horn length significantly influences first-year survival and fecundity, but the effects vary across environmental conditions and years of birth. For survival, the impact of horn length is modulated by both environmental quality and population density. In contrast, the fecundity models show less variability and no significant evidence of fluctuating selection. These findings contribute to our understanding of how horn length affects the fitness of Soay sheep in different environmental contexts.
