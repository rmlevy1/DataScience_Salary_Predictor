# Data Science Salary Predictor

## Goal: 
Create a prediction model that will predict Data Analyst, Data Engineer, Machine Learning Engineer, Data Scientist salaries based off personalized criteria (i.e.experience, skills, location, size of company, revenue of company, state)

## Social Case: 
Help those landing a Data Science job negotiate their salary based off personalized criteria.


## Process:
#### Acquiring Data
Scraped ~1,500 jobs from Glassdoor via selenium
(Received help from this blog post https://towardsdatascience.com/selenium-tutorial-scraping-glassdoor-com-in-10-minutes-3d0915c6d905)
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
* Created a function to categorize job titles in to either 
  * data analyst
  * data scientist
  * data engineer 
  * machine learning engineer
* Created a column for average salary by taking a the min of salary range and max of salary range from salary estimate and dividing by 2 
* Created a column for job description word count
* Filled in all missing company size, sector, and type of ownership values with data fromn LinkedIn
* Filled in all missing values in revenue with data from Owler
* Created a column for job being located in headquarters or not
* Created a column for company having internation heaquarters or not
* Created a column for company age
* Created a function to categorize jobs into 3 different seniority groups 
  * 0-2 Yrs Experience
  * 2-5 Yrs Experience
  * 5+ Yrs Experience
* Created a column for mentions of Bachelor's, Master's or PhD in job description
* Created columns for a variety of skills mentioned in job descriptions(i.e. python, sql, scipy, pytorch, docker, aws and etc)

#### EDA
I looked at the Features vs Average Salary and Features vs Value Counts.
A few highlights below.
