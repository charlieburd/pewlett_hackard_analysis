# Module 7 - Pewlett Hackard Analysis

## Overview of Pewlett Hackard Analysis


#### The Pewlett Hackard Module was to teach the basics of Postgres SQL. We began with creating a ERD (Entity Relationship Diagram) from Quick DBD to act as a map. Once we understood the relationships of all the data, we could start creating tables, referring to the ERD to see which tables had which data we wanted and why kind of data it was. As we created the tables, we learned the basics of SQL language, like SELECT, FROM and WHERE. Once we began joining data from different tables we also learn INTO, GROUP BY, ORDER BY and the different types of JOINS. Once we had the understanding of those functions we could dive into the challenge.

#### The Pewlett Hackard Analysis taught us how to implement the different functions we learned in the module without giving us the code to reference. The goal of the analysis was to:
#### a) Determine the number of retiring employees per title
#### b) Identify employees who are eligible to participate in a mentorship program
#### In this challenge  we used all of the functions mentioned above with the addition of DISTINCT ON, which allowed us to display the most recent title for employees that were coming up on retirement, throwing out any old titles.


## Pewlett Hackard Analysis Results
### Deliverable 1
 * The two most common titles that are nearing retirement are both senior positions, Senior Engineer and Senior Staff. This could be good news for Pewlett Hackard mentor program as the salaries for these roles would be higher compared to non-senior roles. When these employees do transition out of their roles, the company will have extra cash to invest in the mentorship program for a smoother transition.
 
 * From 1/1/2000 - 12/31/2002 only 16,074 employees retired, 2002 is the last year data was reported so it is likely that this was reported in 2003. The time span we took into account for retirement eligible employees was also 3 years and returned 90,398 employees. I think it is unlikely that you would see a spike of 5X the number of retirees, so perhaps a survey would help the company get a better idea of who will be retiring soon rather than an arbitrary birth year range.

### Deliverable 2
 * Based on our retirement eligibility criteria, there are 1,549 employees that could be mentors. If Pewlett Hackard is planning on 90,000 retirees, they may want to expand the criteria of those that are mentor eligible. A 1-to-60 mentorship ratio does not sound like a very intimate mentorship program. Additionally, this is assuming everyone that is eligible would want to be involved in the program.

 * While there are 29,414 Senior Engineers and 14,222 Engineers eligible for retirement, there are 308 Senior Engineers and 384 Engineers eligible for the mentor program. If Pewlett Hackard is to expand their mentorship criteria, they should focus on Senior Engineers, as they will have the most roles to fill but a relatively small number of mentors.
#### Retirement Count by Title
![stacked_launch_outcomes](https://github.com/charlieburd/pewlett_hackard_analysis/blob/main/png/retirement_count.png)

#### Mentoring Count by Title
![stacked_launch_outcomes](https://github.com/charlieburd/pewlett_hackard_analysis/blob/main/png/mentorship_count.png)
#


## Pewlett Hackard Analysis Summary:

### How many roles will need to be filled as the "silver tsunami" begins to make an impact?
#### If we look at our "retiring_titles" tables, we get the count for each department, after we change the code to below, it will display the total amount of roles that will need to be filled. There are 90,398 roles that will need to be filled.
`SELECT COUNT (title)
FROM unique_titles;`
### Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?
#### No, as I had mentioned in fourth bullet above, there will be a sever lack of mentors, given the large number of roles needed to be filled it would be a challenge to provide enough mentors for all the open roles, even if it were in groups. Some mentor to mentee ratio of departments will be as high as 1-60. To look at this table we will use the below code:
`SELECT COUNT (title), title
FROM mentorship_eligibility
GROUP BY title
ORDER BY count DESC;`
