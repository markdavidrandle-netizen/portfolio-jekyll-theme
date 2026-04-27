---
layout: post
title: "BankSIM Fraud Detection: Data Cleaning and Initial Exploration"
---

## Overview

In this project, I worked with the BankSIM dataset to prepare transactional data for fraud detection modelling. The objective at this stage was to clean the data, validate its quality, and perform initial exploration to better understand key patterns—particularly given the highly imbalanced nature of fraud detection problems.

---

## Dataset Summary

The dataset contains simulated financial transactions, including:

- Customer and merchant identifiers  
- Transaction amount  
- Category of transaction  
- Demographic features (age, gender)  
- Fraud flag (target variable)  

Given the nature of fraud detection, one of the key challenges is the **extreme class imbalance**, where fraudulent transactions represent only a very small proportion of the data.

---

## Data Cleaning

### 1. Data Types

Initial inspection showed that some columns required type conversion:

- `age` was stored as an object rather than numeric  
- Other categorical fields required consistent formatting  

Ensuring correct data types is essential for both analysis and machine learning models.

---

### 2. Missing Values

A full check for missing values showed:

- No null values present across the dataset  

This simplified the cleaning process and allowed focus on feature understanding rather than imputation.

---

### 3. Duplicate Records

Duplicate checks confirmed:

- No duplicate transactions present  

This ensured that transaction counts and aggregations would not be distorted.

---

## Exploratory Insights

### Transaction Distribution

Transaction amounts showed a **skewed distribution**, with most transactions occurring at lower values. This is typical in financial datasets and has implications for fraud detection, as fraudulent transactions often occur at smaller, less noticeable amounts.

---

### Category Analysis

Analysis of transaction categories revealed:

- Some categories have **very high fraud rates**, but with low transaction volumes  
- Others (e.g. transportation) dominate the dataset but show little to no fraud  

This highlights an important issue:

> High fraud rates in small categories may not be statistically reliable.

---

### Class Imbalance

Fraud is extremely rare in the dataset:

- The majority of transactions are legitimate  
- Some categories contain **zero fraudulent cases despite high volume**

This creates a classic **needle-in-a-haystack problem**, where accuracy alone is not a useful performance metric.

Instead, future modelling will focus on:

- Precision  
- Recall  
- F1-score  

---

## Key Takeaways

- The dataset is **clean and ready for modelling**, with no missing or duplicate data  
- Fraud detection is complicated by **severe class imbalance**  
- Transaction behaviour varies significantly by category  
- Simple metrics like accuracy will be misleading in this context  

---

## Next Steps

The next phase of the project will focus on:

- Feature engineering (e.g. transaction frequency, fraud rates by category)  
- Handling class imbalance (sampling techniques)  
- Building and evaluating machine learning models for fraud detection  

---

## Conclusion

This stage of the project established a solid foundation for modelling by ensuring the dataset is clean and well understood. The insights gained—particularly around class imbalance and category behaviour—will directly inform the modelling strategy in subsequent steps.

---
