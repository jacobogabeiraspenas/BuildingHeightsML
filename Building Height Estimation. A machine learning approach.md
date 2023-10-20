# Introduction

Urban meteorology studies are essential for understanding and predicting complex weather patterns and climate dynamics in urban environments. Precise urban morphology data is crucial due to the significant impact of urban structures on local weather and climate. Building heights, layouts, and distribution directly influence factors like temperature, wind flow, and precipitation, making them vital components of urban meteorological models.

Obtaining building data is challenging due to data availability, quality, privacy, cost, and integration issues. Building data can be accessed from sources like OpenStreetMap (OSM), Microsoft Building Footprints, Google Maps, government platforms, and local municipal open data portals.

This document outlines a novel methodology for estimating building heights, primarily for urban climate and weather research but also applicable to urban planning.

The study demonstrates the potential of this approach in improving height estimations compared to traditional methods based solely on local climate zones. Future work may involve extending this methodology to multiple cities and integrating it into existing meteorological modeling frameworks.

# Methodology

## 1. Data Collection

We source building data from two primary providers: OpenStreetMaps (OSM) and the Microsoft Building Footprints API, each contributing distinct attributes.

### OpenStreetMaps (OSM)

- Provides detailed height information for buildings.
- Lacks comprehensive building data, particularly in terms of coverage.

### Microsoft Building Footprints (MBF)

- Offers extensive building footprints, covering a larger number of buildings.
- Lacks specific building height information.

The combination of these data sources bridges their individual gaps, allowing us to harness the advantages of both.

## 2. Domain of Study

The experiment was carried out in Sydney, serving as a key motivator for this study. The selected study area is depicted in Figure 1. In this region, OSM data provides a comprehensive building dataset, including geometry and height information, covering only around 30% of the buildings present in the MBF dataset, which could affect the model's performance.

Two experiments have been conducted, one using data solely from the Sydney domain (around 180,000 buildings) and the other including a similar-sized domain in Grenoble (approximately 200,000 buildings), which significantly enhanced the model's performance.

## 3. Model and Approach Comparison

Our methodology involves comparing two approaches for building height estimation.

### Local Climate Zones Approach

In the conventional approach, building heights are estimated by assigning a single, average value to each building based on its specific local climate zone, in accordance with the values provided in the WUDAPT project's tables.

### XGBoost Model

We employ an XGBoost machine learning model, utilizing features such as building area, perimeter, and location (latitude and longitude) to predict building heights. The first experiment is conducted on a training set of 140,000 buildings for Sydney, and for the second experiment, the set is extended with 200,000 buildings from the Grenoble area.

The evaluation of both methods is done on a test sample of 40,000 buildings. By evaluating the accuracy and effectiveness of the XGBoost model against the local climate zones approach, we determine the most reliable and accurate approach for building height estimation for urban climate modeling purposes.

# Results

The results from both approaches are shown in Table 1. The LCZ approach estimates building height with a MAE of 8.5 m, the XGBoost first experiment shows an MAE of 5.3 m, and the XGBoost second experiment an MAE of 2.3 m.
