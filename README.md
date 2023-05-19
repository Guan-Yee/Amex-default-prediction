# Amex-default-prediction

The dataset is obtained from the Kaggle American Express Competition. The original sizes of the datasets are 16.39GB and 33.89GB respectively for the train and test datasets. To keep the training and test datasets small in size, modifications to the float format and conversion to Parquet format were performed. These modifications were implemented by Kaggle user [Raddar](https://www.kaggle.com/datasets/raddar/amex-data-integer-dtypes-parquet-format). The cleaning scripts to shrink the train and test data sizes can be found in this [train_link](https://www.kaggle.com/code/raddar/amex-data-int-types-train) and [test_link](https://www.kaggle.com/code/raddar/amex-data-int-types-test). 


Mutual Information (for both categorical and numerical variables) and Chi-square tests (for categorical variables) were conducted to reduce the number of features to 126. ADASYN sampling was applied to the training dataset to address the imbalanced minority class 'Default'. Subsequently, Random Forest, LGBM, XGBoost, CatBoost, and Tabnet were trained on both the baseline and ADASYN-sampled training datasets. CatBoost emerged as the best-performing model with accuracies of 85.75% (Baseline) and 85.52% (ADASYN).

Lastly, the following columns were identified as significant predictors affecting the Default prediction outcome: `B_9`, `R_3`, `D_47`, `B_10`, `D_129`, `B_19`, `D_51`, `D_63_3` and `S_5`.

## References
* American Express - Default Prediction Competition [Kaggle](https://www.kaggle.com/competitions/amex-default-prediction/overview)
* Raddar Description of the datasets [Discussion](https://www.kaggle.com/competitions/amex-default-prediction/discussion/328514)