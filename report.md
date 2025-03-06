# Customer forecasting for promotional campaigns report

## About my team
Team name: HVAInternational 
Members:
- Pham Dang Hung: 25% contribution
- Le Xuan Trong: 25% contribution
- Pham Ha Khanh Chi: 25% contribution
- Le Ky Nam: 25% contribution

## Data

### Dataset Overview
- **Data information:** The data has 1946 rows × 28 columns, with ‘CROSS_SELL_SUCCESS’ is the target variable.
- **Missing values:** We didn’t find any missing values in this dataset.
- **Data allocation:**
  + The types of the useful variables within X set:
```
#   Column                       Non-Null Count  Dtype  
---  ------                       --------------  -----  
 0   REVENUE                      1946 non-null   float64
 1   TOTAL_MEALS_ORDERED          1946 non-null   int64  
 2   UNIQUE_MEALS_PURCH           1946 non-null   int64  
 3   CONTACTS_W_CUSTOMER_SERVICE  1946 non-null   int64  
 4   PRODUCT_CATEGORIES_VIEWED    1946 non-null   int64  
 5   AVG_TIME_PER_SITE_VISIT      1946 non-null   float64
 6   MOBILE_NUMBER                1946 non-null   int64  
 7   CANCELLATIONS_BEFORE_NOON    1946 non-null   int64  
 8   CANCELLATIONS_AFTER_NOON     1946 non-null   int64  
 9   TASTES_AND_PREFERENCES       1946 non-null   int64  
 10  PC_LOGINS                    1946 non-null   int64  
 11  MOBILE_LOGINS                1946 non-null   int64  
 12  WEEKLY_PLAN                  1946 non-null   int64  
 13  EARLY_DELIVERIES             1946 non-null   int64  
 14  LATE_DELIVERIES              1946 non-null   int64  
 15  PACKAGE_LOCKER               1946 non-null   int64  
 16  REFRIGERATED_LOCKER          1946 non-null   int64  
 17  AVG_PREP_VID_TIME            1946 non-null   float64
 18  LARGEST_ORDER_SIZE           1946 non-null   int64  
 19  MASTER_CLASSES_ATTENDED      1946 non-null   int64  
 20  MEDIAN_MEAL_RATING           1946 non-null   int64  
 21  AVG_CLICKS_PER_VISIT         1946 non-null   int64  
 22  TOTAL_PHOTOS_VIEWED          1946 non-null   int64 
```
  + In the target set: **Value 1 appears 1321 times (68%)** compared to **625 times of value 0 (32%)**. It shows that there exists an imbalance in the given data set.

### Data Visualizations
- Table:

| REVENUE | CROSS_SELL_SUCCESS | NAME | EMAIL | FIRST_NAME | FAMILY_NAME | TOTAL_MEALS_ORDERED | UNIQUE_MEALS_PURCH | CONTACTS_W_CUSTOMER_SERVICE | PRODUCT_CATEGORIES_VIEWED | ... | LATE_DELIVERIES | EARLY_DELIVERIES | PACKAGE_LOCKER | REFRIGERATED_LOCKER | AVG_PREP_VID_TIME | LARGEST_ORDER_SIZE | MASTER_CLASSES_ATTENDED | MEDIAN_MEAL_RATING | AVG_CLICKS_PER_VISIT | TOTAL_PHOTOS_VIEWED |
|---------|--------------------|------|-------|------------|-------------|---------------------|-------------------|----------------------------|-------------------------|-----|---------------|---------------|---------------|------------------|----------------|----------------|----------------------|------------------|------------------|------------------|
| 393.0   | 1                  | Saathos | saathos@unitedhealth.com | Saathos | Saathos | 14.0 | 6.0 | 12.0 | 10.0 | ... | 2.0 | 0.0 | 0.0 | 0.0 | 33.4 | 1.0 | 0.0 | 1.0 | 17.0 | 0.0 |
| 1365.0  | 1                  | Alysanne Osgrey | alysanne.osgrey@ge.org | Alysanne | Osgrey | 87.0 | 3.0 | 8.0 | 8.0 | ... | 2.0 | 0.0 | 0.0 | 0.0 | 84.8 | 1.0 | 0.0 | 3.0 | 13.0 | 170.0 |
| 800.0   | 1                  | Edwyd Fossoway | edwyd.fossoway@jnj.com | Edwyd | Fossoway | 15.0 | 7.0 | 11.0 | 5.0 | ... | 1.0 | 0.0 | 0.0 | 0.0 | 63.0 | 1.0 | 0.0 | 2.0 | 16.0 | 0.0 |
| 600.0   | 1                  | Eleyna Westerling | eleyna.westerling@ge.org | Eleyna | Westerling | 13.0 | 6.0 | 11.0 | 5.0 | ... | 3.0 | 0.0 | 0.0 | 0.0 | 43.8 | 1.0 | 0.0 | 2.0 | 14.0 | 0.0 |
| 1490.0  | 1                  | Elyn Norridge | elyn.norridge@jnj.com | Elyn | Norridge | 47.0 | 8.0 | 6.0 | 10.0 | ... | 8.0 | 0.0 | 0.0 | 0.0 | 84.8 | 1.0 | 1.0 | 3.0 | 12.0 | 205.0 |
| ...     | ...                | ...  | ...   | ...        | ...         | ...                 | ...               | ...                        | ...                     | ... | ...           | ...           | ...           | ...              | ...            | ...            | ...                  | ...              | ...              | ...              |
| 3450.0  | 0                  | Obara Sand | obara.sand@yahoo.com | Obara | Sand | 87.0 | 8.0 | 8.0 | 7.0 | ... | 3.0 | 0.0 | 0.0 | 0.0 | 212.5 | 10.0 | 2.0 | 3.0 | 11.0 | 0.0 |
| 5829.0  | 0                  | Quentyn Blackwood | quentyn.blackwood@yahoo.com | Quentyn | Blackwood | 244.0 | 4.0 | 7.0 | 2.0 | ... | 3.0 | 0.0 | 0.0 | 0.0 | 282.2 | 10.0 | 1.0 | 4.0 | 10.0 | 424.0 |
| 1900.0  | 0                  | Rhonda Rowan | rhonda.rowan@gmail.com | Rhonda | Rowan | 57.0 | 2.0 | 8.0 | 4.0 | ... | 7.0 | 3.0 | 0.0 | 0.0 | 254.4 | 10.0 | 0.0 | 4.0 | 12.0 | 480.0 |
| 1600.0  | 0                  | Turnip | turnip@yahoo.com | Turnip | Turnip | 74.0 | 3.0 | 10.0 | 10.0 | ... | 3.0 | 0.0 | 0.0 | 0.0 | 564.2 | 10.0 | 3.0 | 3.0 | 11.0 | 796.0 |
| 2050.0  | 1                  | Tommard Heddle | tommard.heddle@merck.com | Tommard | Heddle | 188.0 | 4.0 | 9.0 | 5.0 | ... | 3.0 | 1.0 | 1.0 | 0.0 | 248.0 | 11.0 | 2.0 | 3.0 | 12.0 | 0.0 | 

- Histogram
![image](https://github.com/user-attachments/assets/67aa6b16-afda-49ce-b770-b07fd3b21be9)
-> Most values fall within 500 - 6000, peaking around 1500. The distribution shows **2 adjacent Gaussian shapes**, suggesting that the features follow an approximately normal distribution.

![image](https://github.com/user-attachments/assets/4d1081db-bbae-4425-a3b8-5eb329353e6d)
-> Most values fall within 0 - 300, peaking around 50. The distribution exhibits a **right-skewed shape**.

![image](https://github.com/user-attachments/assets/aef7dddd-428f-4898-9146-4ccfd64f9142)
-> Most values fall within 0 - 250, peaking around 100. The distribution forms a roughly Gaussian shape, suggesting that the features follow an approximately normal distribution.

![image](https://github.com/user-attachments/assets/8e5af18d-9c20-4f09-b882-ac18e9f6cfeb)
-> Most values fall within 60 - 300, peaking around 150. The distributions exhibit a roughly Gaussian shape, except an unusual increase at approximately 100, suggesting that the features follow an approximately normal distribution.

#### Overall, although there are a lot of outliers shown in these histograms, most are natural outliers, still following the overall distribution of data. This means these histograms display very few extreme outliers.

- Heatmap (Correlation Matrix):
![image](https://github.com/user-attachments/assets/1403a8b9-40de-4592-8891-32a38f894a68)
  +  The features that have the highest correlation with CROSS_SELL_SUCCESS in decreasing order are CANCELLATIONS_BEFORE_NOON, MOBILE_NUMBER, TASTES_AND_PREFERENCES, REFRIGERATED_LOCKER, ... However the correlation are quite low, within 7% - 16%
  +  The features MOBILE_LOGINS, PC_LOGINS, AVG_PREP_VID_TIME, AVG_CLICKS_PER_VISIT also influence the CROSS_SELL_SUCCESS but to a lesser extent.
  +  The features with little to no correlation with CROSS_SELL_SUCCESS , which can be removed, are REVENUE, UNIQUE_MEALS_PURCH, PRODUCT_CATEGORIES_VIEWED

## Solutions

## Results
