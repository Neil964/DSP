# Data Science Project

## Projects

### Project Background - Working From Home Burnout

Since Covid more people have been working from home.  This project has been taken from surveyed data for people who work from home to see what factors affect the risk of burnout.

Every person is different and can handle stress in different ways and have different lifestyles. This project is to try and highlight if there are any significant factors that affects everyone in the same way therefore creating a risk of ‘burnout’.

The data was initially split into Low, Medium and High categories for burn out, and this has now been amended to show only Low and have combined both Medium/High into one category to specifically check for anything which may result in a burnout score which is not Low.  Additionally, by doing this, the data has been more evenly spread for machine learning use.

### Data Infrastructure and Tools

The dataset has been extracted from Kaggle: https://www.kaggle.com/datasets/aryanmdev/remote-work-burnout-and-social-isolation-2026/data

The dataset has 2000 rows of data which comprises of various aspects in a working day that may affect an individual’s chance of burnout.  No personal identifiable information is held in the data.

Nothing states that this is manufactured data.  The data does need to be checked and cleansed appropriately, checking for missing data and removing any duplications, null values etc.

The ETL process is that the data has been extracted in Excel format and Python will be the main application to cleanse and apply relevant statistical analysis and visualisations and to apply linear regression.

### Data Engineering

The data has been checked and cleansed for:
•	Null values – none found 
•	Duplications – none found
•	Correct Data Types none found 
•	Possible Outliers – outliers found but based on the data these are minimal but relevant within the data


![datatypenulls](assets/NO%20NULL%20DATA.png)

![duplicated](assets/DUPLICATED.png)

No further cleansing needed to be applied to the data.

The ‘burnout risk’ was initially split into ‘low’, ‘medium’ and ‘high’ categories.  With the project attempting to identify a potential risk of burnout, the data has been amended to merge both medium and high risk together, shown as 1 for ‘Low’ and 2 for ‘Medium/High’ and by doing so provides a more even split between the low risk and higher risk areas for modelling accuracy.


![balance](assets/BALANCED%20TEST%20DATA.png)


### DATA VISUALISATIONS:

With a filter applied in Excel, it is easy to see that out of the 2000 rows of data, there appear to be multiple User Id's in the data, with which on varying days the same user can show a different burn out risk/score.

In total there were 150 User Id's within the data.

![users](assets/DISTINCT%20USER%20COUNT.png)

Due to the distinct User Id's and to fully understand how Burnout is affecting the surveyed employees, a count of Users was applied for User Id’s who only work weekdays.  In total only 7 users did not work on a weekend.

![noweekends](assets/NO%20WEEKENDS.png)

In total there were zero users who only worked weekends which highlights that all users will only work weekdays.

![weekendsonly](assets/WEEKEND%20ONLY.png)

The below provides a count of users and a count of the number of weekdays and weekends that the users provided in the data.  As it shows, the data is quite varied with a small selection of users working either 2 weekdays or at most 21 weekdays and also confirms the 7 users who did not work on weekend.

![workingdays](assets/WEEKENDS%20PER%20USER.png)

With the data being split into 'Low' and 'Medium/High' being combined, the data clearly identifies that there is an issue with burnout with people who work weekends, but also identifies that a very large proportion of people who work weekdays are at risk of medium to high burnout.

![burnout](assets/TEST.png)

### DATA ANALYTICS

Linear Regression is the model that was used in the data to try and highlight which fields directly affect the ‘Burnout Score’ ultimately providing the actual ‘Burnout Risk’.  The higher the score the higher the risk.

Taking all numerical fields into account, the Linear model has provided a breakdown of the importance of each feature (field) against the Burnout Score.

As shown below, sleep hours are the biggest contributor when based against the Burnout Score.  Although this is a negative correlation, this basically states that when a user has less sleep, there is more chance of the Burnout Score being much higher.

Fatigue Score is the 2nd highest correlated contributor to the Burnout Score.  This is suggesting that a higher fatigue score is providing a higher Burnout Score.

After Hours Work is also a large contributor to the Burnout Score confirming that more after hours that are worked will also provide higher Burnout Score.

Although the other features do provide a coefficient value, these values are extremely low and do not have a major impact on the Burnout Score.

![feature](assets/FEATURE%20IMPORTANCE%20FOR%20BURNOUT.png)

To ensure that the Sleep hours are a major contributor to the actual Burnout Score, the below screenshot clearly highlights the strong correlation confirming that the more hours slept decreases the chance of a higher Burnout Score.  As shown below, there are a few outliers in the data but based on the scenario in question, this can happen due to different people and circumstances.

![sleep](assets/SLEEP%20HOURS%20BY%20BURNOUT.png)

To ensure the Linear Regression model is working effectively, the below screenshot, shows the actual Burnout Score values and the values predicted by the model.  It clearly highlights that although the model is interpreting the correlation between the different features, the model does not provide great predictive accuracy due to the deviations of the data varying away from the ‘perfect prediction line’.

![predictedlinear](assets/PREDICTED%20LINEAR%20REGRESSION.png)

A further test on the data took place using the Random Forest model to determine if the same features would be relevant in a different model.

The Random Forest model correctly predicted 100% of the Low Risk and High-Risk outcomes.  This could mean that there is very little data available for any issues to occur, potentially there may be an issue with the model, the data is manufactured for reporting purposes only (which clearly goes against the initial data analysis) and further analysis may need to be applied or the model is working perfectly.

![randomforest](assets/RANDOM%20FOREST%20MODEL.png)

The Random Forest model determined that the ‘Fatigue Score’ was the standout feature that had the most effect on the ‘Burnout Score’, with ‘Sleep Hours’ a far second.  All other features were extremely low in the model.

![predictedforest](assets/PREDICTED%20BY%20RANDOM%20FOREST.png)

### CONCLUSION

In conclusion it is clear to see that the Random Forest model provides a much better fit of the data and therefore would be the best model to be used going forward for predicting ‘Burnout Scores’, once further testing is done on the model due to its initial 100% predictions.

Both models highlighted ‘Fatigue Score’ and ‘Sleep Hours’ as the biggest contributor to ‘burnout’ which is no real surprise and would expect this kind of result.  This is based on limited data and therefore if additional data was added like ‘role’, ‘number of children’, ‘overtime’, ‘starting time’ may make a considerable difference and potentially provide a different outcome.

Overall, further testing on the models would need to take occur to ensure that all is working effectively.




