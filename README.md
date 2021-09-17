# pump-it-up-data-mining-challenge
Github repo link: https://github.com/trajinthan/pump-it-up-data-mining

Competition link: https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/

Submission score in the competition for the last git commit is 0.8088 

**Techniques Applied**

***1. Exploratory Data Analysis***

1. Checked the output labels, count and the shape of the given dataset

2. Analyzed the information of the features such as
      -  data type
      -  number of null values in each columns
      -  count of every distinct values in each columns with respect to output labels

3. Analyzed the relation between some same kind of features 
      -  plotted bar charts
      -  got the counts of each values in each features
      -  grouped the similar features and compared the values they carry
      -  the following features carries similar information
         -  water_quality & quality_group
         -  payment & payment_type
         -  waterpoint_type & waterpoint_type_group
         -  source & source_type & source_class
         -  management & management_group
         -  extraction_type & extraction_type_class & extraction_type_group
         -  region_code & region
 
4. The feature 'recorded_by' has only one distinct value for all ids.

5. Features 'amount_tsh' and 'num_private' contains most number of '0's as values

***2. Preprocessing & Feature Engineering***

1. Dropped unnecessary columns
   - identical or similar columns with less information
   - 'recorded_by' as it has only one distinct value for all ids
   - Dropped 'amount_tsh' and 'num_private'

2. Created new columns 'date_recorded_month' and 'date_recorded_year' from the feature 'date_recorded'

3. Replaced 0 values(outliers) in the feature 'longitude' with the mean value of the same feature

4. Replaced null/missing values 
   - for categorical columns, replaced with ('n/a') as theose columns have very few null values
   - for features 'permit' and 'public_meeting' replaced with most occuring value
      - In those features the count value 'true' is very higher than the count of value 'false'. So           replaced the null values with 'true'

5. Encoded categorical columns
   - applied label encoding for categorical features

 ***3. Model selection***
- Analyzed CATboost, XGBoost and RandomForest classifiers
- Tuned parameters using GridSearchCV
- Plotted feature importance graph

RandomForest classifier resulted in accuracy of 0.82
