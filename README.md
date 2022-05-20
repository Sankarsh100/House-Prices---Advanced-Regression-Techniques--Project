# House-Prices---Advanced-Regression-Techniques--Project
Joanna Broniarek

The goal of this repository was to provide an analysis for Kaggle's competition: https://www.kaggle.com/c/house-prices-advanced-regression-techniques

kaggle-image

My best score on the Kaggle Leaderboard: 0.14906

Description
EDA and Data tidying:

Removing columns that contain the same value in 100% ["Street", "Utilities"]
Removing outliers : GrLivArea more than 4500.
Improving values like Year more than 2017.
Handling missing numerical values:
LotFrontage according to median in specific Neighborhood
With constant = 0 for : ['BsmtFinSF1', 'BsmtFinSF2', 'BsmtFullBath', 'BsmtHalfBath', "MasVnrArea"]
The rest of numerical columns (apart from point 5) with median.
Transformation of some numerical features that are actually categorical: ['MSSubClass', 'OverallCond’]
Handling missing categorical values. (specific for each feature)
Transformation of skewed features:
SalePrice – log transformation
Other features with skeweness > 0.5 using BoxCox transformation
Transformation some categorical features (with specific order) into numerical
Feature Engineering:

Feature Isgarage defined according to feature GarageArea (1 – if more than 0)
Feature Isfireplace defined according to feature Fireplaces (if more than 0)
Feature Ispool defined according to feature PoolArea (if more than 0)
Feature Issecondfloor defined according to feature 2ndFlrSF (if more than 0)
Feature IsOpenPorch defined according to feature OpenPorchSF (if more than 0)
Feature IsWoodDeck defined according to feature WoodDeckSF (if more than 0)
Feature TotalSqrtFeet defined as sum of GrLivArea and TotalBsmtSF
Feature TotalBaths defined as BsmtFullBath + FullBath + BsmtHalfBath/2 + HalfBath/2.
Feature Neighborhood (transformation into 0, 1, 2) according to statistics if specific Neighborhood is rather rich/poor or between them.
One-Hot Encoding for categorical data
Modelization:

Scaling - RobustScaler

Linear Regression
LASSO model selection
GradientBoostingRegressor
XGBRegressor
ElasticNet
LGBMRegressor
BaggingRegressor
Training:

StackingCVRegressor on models: [Lasso, ElasticNet, XGB, LGBM]
Weighted predictions 0.2ElasticNet + 0.25lasso + 0.15LGBM + 0.4StackedModels
Environment specification:
python 3.6.4
numpy 1.14.2
scipy 1.1.0rc1
seaborn 0.9.0
sklearn 0.20.1
pandas 0.22.0
sklearn 0.20.1
xgboost 0.72
lightgbm 2.2.2
