# Data Science Salary Predictor

## Goal: 
Create a prediction model that will predict Data Analyst, Data Engineer, Machine Learning Engineer, Data Scientist salaries based off personalized criteria (i.e.experience, skills, location, size of company, revenue of company, state)

## Social Case: 
Help those landing a Data Science job negotiate their salary based off personalized criteria.


## Process:
#### Acquiring Data
Scraped ~1,500 jobs from Glassdoor via selenium\
(Received help from this blog post https://towardsdatascience.com/selenium-tutorial-scraping-glassdoor-com-in-10-minutes-3d0915c6d905) \
Scraped the following information from each job posting
* Job Title
* Salary Estimate
* Job Description
* Rating
* Company Name
* Location
* Headquarters Location
* Company Size (Employees)
* Year company founded
* Type of Ownership
* Sector
* Revenue

#### Data Cleaning & Feature Engineering
* Created a function to categorize job titles in to either:
  * data analyst
  * data scientist
  * data engineer 
  * machine learning engineer
* Created a feature for average salary by taking a the min of salary range and max of salary range from salary estimate and dividing by 2 
* Created a feature for job description word count
* Filled in all missing company size, sector, and type of ownership values with data fromn LinkedIn
* Filled in all missing values in revenue with data from Owler
* Created a feature for job being located in headquarters or not
* Created a feature for company having internation heaquarters or not
* Created a feature for company age
* Created a function to categorize jobs into 3 different seniority groups 
  * 0-2 Yrs Experience
  * 2-5 Yrs Experience
  * 5+ Yrs Experience
* Created a feature for mentions of Bachelor's, Master's or PhD in job description
* Created features for a variety of skills mentioned in job descriptions(i.e. python, sql, scipy, pytorch, docker, aws and etc)

#### EDA
I looked at the Features vs Average Salary and Features vs Value Counts.
A few highlights below.
<img src="Project%20Images/Comp_Size.png" width="300">
<img src="Project%20Images/Job_Titles.png" width="300">
<img src="Project%20Images/Seniority.png" width="300">

#### Modeling
One hot encoded all the categorical variables, creating 140 columns. 
Performed a train-test split of 20%.

Baseline Model was Multiple Linear Regressiong and the metric I used was Mean Absolute Error for its interpretability.\
Below are the four models I used and their Mean Absolute Error Scores. (Used a cross validation score of 20)
 * Multiple Linear Regression - 22.16
 * Lasso - 20.78
 * Ridge - 22.08
 * Random Forest - 22.00 

#### Results
The Lasso model performed the best with a mean absolute error of ~20 meaning that its predictions were about $20,000 off from othe actual salaries. I don't think these results are that awful given that glassdoor provides a pretty wide salary range.

#### Further Work
A lot more data is required for this model to be very accurate.
Around ~1,500 jobs is not enough. \
Would like to create an web facing api for people to enter their personalized job criteria and the interface would spit out a predicted salary based off a large set of data (~1,000,000).

#### Slides
https://docs.google.com/presentation/d/1XiKExI6fY0AYU-il6l1-6o2bkgk8NSuOgG5JwhFysVg/edit?usp=sharing
