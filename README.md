# Visual_Analytics
Project from Visual Analytics cource assignment
Part1 - In this part, I am going to customize settings of ‘html_output’ and ‘pdf_output’ sections of YAML
preamble of _HomeExam30_CandNo.Rmd template file to add a personal flavor and compile the document into
popular output formats (e.g., ‘html_output’, ‘pdf_output’ and ‘slidy_presentation’) with a use of ‘Knit’
command.  

Part2 - In this part, I am going to demonstrate skills to present data in a visual form with ggplot2 library.

Part3 - Writing a story about COVID-19
There are five components of Healthcare data that are tracked on daily basis (infected, admissions, in respirator, covid tests and covid death), three components of Economics data that are also tracked on daily basis (business compensation scheme, unemployment benefits and wage compensation) and Mobility data from apple and android mobile devices that are collected to reveal changes in mobility trends over the time affected by Covid-19.
Story
Question(s):
Since announcement of the Norwegian Health Minister that the outbreak is “under control” on 6 April, 2020, which administrative regions in Norway have reported the most percentage of Covid-19 cases per population, and how has the cases for these regions changed over time?

Introduction:
We are working with Covid-19 tracking dataset, which contains more than 274000 observations with number of cases, which is extracted daily at 4 AM from 26.03.2020 for all Norway municipalities and regions. Each row of the dataset represents the number of cases at a certain time in a certain kommune. The dataset contains 8 columns that provide the date, time, location, location number, Covid-19 cases and population.

To determine how the number of Covid-19 cases per population has changed over the time in the kommunes with the highest number of reported cases, we will be working with the following columns:

kommune_name: municipality in which the number of cases was checked
date: the date when case data was renewed
cases: the reported Covid-19 number of cases 
Approach:
Our approach is to fist determine which municipalities have the highest number of Covid-19 cases. Next, we will visualize the number of cases per population across the time for the top six regions using a geometric line. The alternative to a line plot could be a scatter plot. However, since our data is continuous, a scatter plot does not seem appropriate here.

To look at the kommunes with the highest number of Covid-19 cases per population, these function will be applied:

replace_with_na and na.omit() to replate 0 to NA and delete these raws
filter() to extract only the results after 6 April, 2020
group_by() to separate data to show the top cases for each top municipality
mutate() to count the percentage of cases per population
summarise() to find the maximum percentage in each municipality
arrange() and desc() to sort the table by descending count
slice() to keep the top municipalities with the highest number of reported Covid-19 cases per population
To plot the number of Covid-19 cases per population over time, we will use the following functions:

filter() to reduce the dataset to the top komunnes with the highest percentage and to all results after 6 April, 2020
count() to count the number of observations per year and city
mutate() to count percentage
geom_line() to create a line plot of Covid-19 cases for each day and to add a line with average percentage value for each day
facet_wrap() to create scatter plot facets for each kommune
