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
* Rating
* Company
* Location
* Headquarters Location
* Sector
* Industry
* Company Size (Employees)
* Revenue
* Type of Ownership
* Year company founded
