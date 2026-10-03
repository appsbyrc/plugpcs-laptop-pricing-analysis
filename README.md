# Laptop Hardware and Pricing Analysis with Linear Regression

## Project Overview

This project examines whether common laptop hardware specifications can help explain laptop price.

The analysis uses a cleaned dataset of laptops collected from Plug PCs and builds a baseline linear regression model using RAM, storage, screen size, CPU brand, and GPU brand.

## Project Goal

The main question is:

**Can common laptop hardware specifications help predict laptop price?**

This first model is intended as a baseline. CPU and GPU brand are broad categories and do not capture the differences between individual processor and graphics card models.

## Data Preparation

The modeling dataset contained 1,477 laptop records.

For this analysis:

- Screen size was extracted from product descriptions and laptop names
- 1,350 laptops had a usable screen size
- 11 specialized configurations priced above $8,000 were excluded from this baseline model
- The final Slice 1 dataset contained 1,339 laptops

The full modeling dataset was preserved.

## Features

The model used:

- RAM capacity
- Storage capacity
- Screen size
- CPU brand
- GPU brand

The target variable was laptop price.

CPU and GPU brand were converted into dummy variables before modeling.

## Modeling

The data was divided into:

- 80% training data
- 20% testing data

A Scikit-learn `LinearRegression` model was trained on the training data and evaluated on both the training and testing sets.

## Results

- Training R-squared: 0.556
- Testing R-squared: 0.597
- Training MAE: about $611
- Testing MAE: about $578

The similar training and testing results suggest that the model is not showing obvious overfitting.

## Interpretation

The model explains a meaningful portion of laptop price variation, but it is not accurate enough for precise pricing.

RAM and screen size showed positive relationships with predicted price. NVIDIA GPU presence was also associated with higher predicted prices relative to the reference GPU category.

Broad CPU and GPU brand categories are limited because they do not distinguish between lower performance and higher performance hardware within the same brand.

## Limitations

This is a baseline linear model.

Important factors such as detailed CPU model, GPU model, product tier, display quality, build quality, and other hardware characteristics are not fully represented.

Future work could use more detailed CPU and GPU information to improve the model.

## Tools Used

- Python
- Pandas
- Matplotlib
- Scikit-learn
- Google Colab

## Files

- `PlugPCs_Laptop_Price_Modeling.ipynb`
- `data/plugpcs_laptops_model_2026-09-29.csv`
