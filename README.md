# income_predictor_group_project
# Team 203

- Removed duplicated rows (56862 rows. 86500 after removing the 'Instance' column)
- Removed NaNs from 'Year of Record' column (~ 4000)
- **NOTE:** 'Year of Record' , 'Housing Situation' are good features to consider
- **NOTE** 'Crime Level' doesn't look like it's correlating with 'Total Income'

.........

- The given data is synthetic ie not based on real data so there is a possibility that your hair color effects your income
- **SCORE:** Mean Absolute Error
- The data was pre-processed such as dealing with NaNs, removing repeated rows and encoding categorical features. For the latter, TargetEncoder and sklearn's LabelEncoder were used. TargetEncoder yielded much better results. Some features were dropped based on the correlation between the features and the target. Not much data preprocessing was done, the work was left to a strong algorithm to work out.
- A number of algorithms were tested. Here is the order of performance from worse to best:
	- Polynomial Regression with degree = 2 (score 1570202.24273)
	- Ridge Regression (Score 79605)
	- (I didn't test with Random Forest Regression but I believe it would have performed better than Ridge) 
	- LightGBM -gradiant boosting (score 13708.404 with LabelEncoder and 10758.372 with TargetEncoding)
