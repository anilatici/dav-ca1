
# Composite Index Development Report

  

## Introduction

  

This document details the development of a composite index for evaluating the livability of urban areas. The index is constructed from multiple indicators grouped into sub indices.

  

## Data Preparation

  

Two datasets were used:

-  `uaScoresDataFrame.csv`: Contains scores across categories such as Housing, Healthcare, Economy, and Education.

-  `movingtoGlobalLiveabilityIndex.csv`: Contains Global Liveability Scores for comparison.

  

Steps taken:

- Dropped non-numeric/identifier columns (`Unnamed: 0`, `UA_Name`, `UA_Country`, etc.).

- Cleaned and standardized `City` and `Country` names.

- Normalized numeric values using min-max scaling to bring all values into a 0–1 range.

  

## Sub-indices and Composite Index Construction

  

Indicators were grouped into four sub indices:

  

-  **Basic Needs**: Housing, Healthcare, Safety, Environmental Quality

-  **Economic Opportunity**: Economy, Startups, Venture Capital, Business Freedom, Taxation

-  **Mobility & Infrastructure**: Travel Connectivity, Commute, Internet Access

-  **Quality of Life**: Leisure & Culture, Education, Tolerance, Outdoors, Cost of Living

  

Each sub index was calculated by taking the mean of the relevant normalized columns.

  

## Principal Component Analysis (PCA)

  

To understand variance in the dataset, PCA was performed.

  

### Scree Plot

The scree plot below shows the cumulative explained variance of the components:

![Scree Plot](/output.png)

  

## Weighted Composite Index

  

Custom weights were assigned to each sub index to reflect importance:

Example:

    weights_basic = {
    
    'Housing': 0.2,
    
    'Healthcare': 0.4,
    
    'Safety': 0.2,
    
    'Environmental Quality': 0.2
    
    }
## Comparison with Global Liveability Index

The `UA Composite Index` was compared against the `Global Liveability Overall Score`.

### Pearson Correlation:

**r = 0.761**

This indicates a strong positive relationship between the constructed index and the global benchmark.

### Scatter Plot

A scatter plot of both scores shows a clear upward trend:
![Scatter Plot](/output-scatterplot.png)

## Correlation Matrix

A matrix was computed to assess relationships between UA sub-indices and Global sub-scores.

                          Stability   Healthcare   Culture & Environment Education  Infrastructure
    Basic_Needs_Index       0.671       0.304                 0.139       0.305           0.320
    Economic_Opportunity    0.571       0.522                 0.369       0.472           0.224
    Mobility_Infrastructure 0.528       0.488                 0.384       0.144           0.564
    Quality_of_Life         0.392       0.412                 0.431       0.268           0.076

Basic Needs index has a strong correlation with stability which indicates that cities with better basic needs have higher stability scores. 

Economic Opportunity index has moderate correlation with stability, healthcare and education. This suggests that cities with better economic opportunities tend to have better healthcare and education systems. 

Mobility Infrastructure index has moderate correlation with stability, healthcare and infrastructure. Highest correlation here is with infrastructure which is expected. 

Quality of Life index has the highest correlation with healthcare and culture & environment but the correlations aren't very high with the highest being 0.431. This still shows that quality of life has a relationship between cultural/environmental factors as well as the quality of the healthcare system. 