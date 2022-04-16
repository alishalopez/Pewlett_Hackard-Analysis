# Pewlett-Hackard Analysis
## Overview of Analysis
Pewlett Hackard is preparing for upcoming retirements so we are assigned this analysis to be ready to offer retirement packages to those eligible and to keep in mind what positions will need to be filled in the future. With this analysis they are able to think ahead and strategically to keep everything running smoothly as employees begin to retire. Previously they had only been using Excel and VBA for the data so we are going to use SQL given the 6 CSV files already given.

## Results
Through the analysis, we were able to find the following:

* There are 41,381 employees eligible for retirement, and 41,381 positions that will need filling once they retire.
* A majority of the employees eligible hold a senior job title, such as Senior Engineer or Senior Staff.
* 1.549 employees have mentorship eligibility.
* There is a giant gap in the amount of employees eligible to retire and employees ready to fill those roles that become vacant.

## Summary
The data was collected to give Pewlett-Hackard a full list of employees eligible to retire, their job titles and insight on what the next step going forward is in preparation.
Creating the unique_titles.csv, we are able to see the most recent title the retiring employees hold and what needs to be filled exactly.

``` SQL
-- Use Dictinct with Orderby to remove duplicate rows
SELECT DISTINCT ON (emp_no) emp_no, 
first_name,
last_name,
title
INTO unique_titles
FROM retirement_titles as rt
WHERE (rt.to_date = '9999-01-01')
ORDER BY emp_no, to_date DESC; 
```
A preview of the table shows below:

![unique_titles](https://github.com/alishalopez/Pewlett_Hackard_Analysis/blob/930bfcd510a74f56ddcd32d7c8a770aa4fa412d2/unique_titles.png)

Looking for young, promising talent to train moving into Senior roles would be beneficial as they can develop and hold senior positions when ready. Running this analysis often to keep count on position openings will keep everyone more accountable to train and develop talent around them so they are able to promote later down the line as retirements happen.
