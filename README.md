# Loan Default Prediction
## Project Report

![](Images/Desk.jpg)

### Project Overview: 

A bank has noticed that their loan defaults for personal loans is very high - nearly 15%. They want to use the data they have been collecting on the loans to try to predict which factors or features are most likely to indicate a high probability of loan default so they can deny those loans. 

#### Data Wrangling:

I started the project by familiarizing myself with the data. The original dataset had 32 features & 50,000 observations with about 25% of the features being categorical. 

Addressing Missing Values: <br>
* 1 loan had nulls for all features and was deleted. 

![](Images/Table%20Images/01_Missing_Value_Summary.png)

* For entries that were missing the value for length, but had a value for employment: I filled in length with the mean of '6 years'. <br>
* For entries with a missing value for employment, but a value for length: I filled in with '0 years'. <br>
* For the remaining that were missing both employment & length, I filled in with 'unemployed' & '0 years'. <br>
* I used the mean to fill in missing values for bcOpen, bcRatio and revolRatio. The mean looked like the best overall representation of the data. 

Looking at the data & checking outliers. <br>
* I checked how many states were represented.  49 total - all but Iowa. California had the most records.
* I noticed there were a few exceptionally high salaries so I checked those out. The ones below $3,000,000 made sense but the two above did not. Because I could not be certain what the error was with the salary, I deleted those two entries.
* I reviewed the remaining features for outliers or any data that appeared to not make sense. Some were much higher than others but they seemed plausible still so I kept them with one exception, see below. 
* Record 22161 looks to be very suspicious. The totalRevLim and totalLim are inconsistent with the rest of their data. I have opted to delete this record.

Creating “Default” & “Current Categories” for “Status” Feature
* I wanted to pare down the different status categories. Next I wanted to look at the different status categories. For the purpose of looking for defaults, I grouped the 7 categories into 3: Current, Late & Default. Since the goal is to predict either Default or Current, I opted to remove all observations in the 'Late' status. Fortunately, this was only 1.6% of the total remaining observations.

![](Images/Table%20Images/02_Loan_Status_Summary.png)

Post cleaning: 49184 observations (no features have been removed yet).

#### Exploratory Data Analysis:

* I noticed some inconsistencies in the ‘Verified’ feature so I corrected them. It is important that the entries align so that there are not extra, unnecessary features created later on when encoding the data. Some entries were listed as “Source Verified” and some were simply “Verified”. 

Additional Features Dropped

![](Images/01_Heatmap.png)


![](Images/)
