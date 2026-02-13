# A-IRB-based Credit Risk Modeling for Portfolio Capital Optimization

## Overview

Under the **Standardized Approach (SA)** of Basel II, banks are required to hold conservative capital against loans and exposures. While this ensures safety, it can tie up significant capital and limit profitability.  

Using **Internal Ratings-Based (IRB)** approaches, banks can estimate their own risk metrics such as **Probability of Default (PD), Loss Given Default (LGD), and Exposure at Default (EAD)** and calculate capital more accurately. This allows banks to manage lower-quality loans more efficiently and scale their business while remaining Basel-compliant.  

This project computes credit risk factors using the **Advanced IRB (A-IRB)** approach, where all credit risk parameters are calculated internally. The dataset used is from Kaggle’s Lending Club loan data.  

**Example:** For a portfolio size of \$8B, our credit model estimates an exposure of \$92M—roughly **1.1% of the portfolio**.


## Project Organization

- **[01_EDA.ipynb](01_EDA.ipynb)** – Exploratory data analysis, checking data types and missing values, and creating dummy variables for categorical features.  
- **[02_data_preparation.ipynb](02_data_preparation.ipynb)** – Fine/coarse classing of continuous variables. Computes **Weight of Evidence (WoE)** and **Information Value (IV)** to identify similar risk groups for coarse classing.  
- **[03_PD_model.ipynb](03_PD_model.ipynb)** – Builds PD model using logistic regression for interpretability. Validates with **ROC-AUC**, **Gini**, and **Kolmogorov-Smirnov** statistics. Generates FICO-style scorecards for customers.  
- **[04_EAD_model.ipynb](04_EAD_model.ipynb)** – Creates EAD model using **Beta regression**. Evaluates performance with **RMSE** and **R²**.  
- **[05_LGD_model.ipynb](05_LGD_model.ipynb)** – Develops LGD model using **Tweedie regression**. Evaluates performance with **RMSE** and **R²**.  
- **[05_EL_model.ipynb](05_EL_model.ipynb)** – Constructs **Expected Loss (EL)** model by combining PD, EAD, and LGD predictions.


## Setup and Run

Clone the repo
```bash
git clone git@github.com:z2gap/credit_risk_modeling.git
cd credit_risk_modeling/
```

Manage dependencies via conda

```bash
conda env create -f environment.yml
conda activate py310_env
```
or pip 

```bash
pip install -r requirements.txt
```

## Download Data

```bash
curl -L -o data/lending-club-loan-data-csv.zip\
  https://www.kaggle.com/api/v1/datasets/download/adarshsng/lending-club-loan-data-csv
<<<<<<< HEAD
```
=======

unzip data/lending-club-loan-data.zip -d data/

rm data/lending-club-loan-data.zip
```
>>>>>>> 50befdbd61be76a64ba6fa198e6ef54f7a82c716
