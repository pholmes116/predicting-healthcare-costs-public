# Comparing Distributed Machine Learning Models for Patient Cost Prediction Using Synthetic Electronic Health Records

This repository contains machine learning distributed pipelines to predict healthcare costs from synthetic patient records. Using cloud infrastructure and Apache Spark, we compare models across both accuracy and runtime, finding Gradient Boosted Trees most precise, while ensemble methods struck the best balance between performance and efficiency.

## Authors

Mayssa Goraieb, Peter Holmes, Vinay Kathard, Nieves Tur de Montis San Gil

## Overview

This study investigates the use of distributed machine learning to predict patient-incurred healthcare costs using synthetic Electronic Health Records (EHRs) generated via Synthea, a MITRE-developed synthetic patient population simulator. Using Apache Spark (PySpark) on Google Cloud Platform with Hadoop Distributed File System (HDFS) for distributed storage, we develop a scalable pipeline to preprocess EHR data and train predictive models. We compare tradeoffs in execution time and predictive accuracy across Linear Regression, Random Forest, Gradient Boosted Trees, and ensemble approaches as the quantity of patient records scale.

## Project Structure

.\
├── Final-Notebooks/\
│   ├── EDA.ipynb\
│   ├── FINAL_ML MODELS_1000_patients.ipynb\
│   ├── FINAL_ML MODELS_100_patients_GCP.ipynb\
│   ├── FINAL_ML_MODELS_100_patients_CPU.ipynb\
│   ├── LDA_and_LR_Modelling_by_topic.ipynb\
│   ├── Notebook for Loading in Synthea Data_1000_patients.ipynb\
│   ├── Notebook for Loading in Synthea Data_100_patients.ipynb\
├── Report.pdf\
└── README.md

## Models

- Linear Regression
- Random Forest
- Gradient Boosted Trees
- Ensemble (LR & RF & GBT)
- Latent Dirichlet Allocation (topic modeling & regression)

## Contact

For questions or contributions, reach out via GitHub Issues or email pholmes116@gmail.com.
