# Kickstarting with Excel

## Overview of Project

### Purpose

The purpose of this analysis is to see how the different fundraising campaigns for theater performed.   
Louise's play *Fever* almost reached its fundraising goal in a short time so we will see how the outcomes are correlated with launch dates and goals.
The outcomes we are looking at are for "successful", "failed", and "canceled". The data is filtered and visualized with graphs in order to find how the theater campaigns fared in these relations.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

I performed the analysis for outcomes based on launch dates with the use of pivot tables and a chart.
The data was filtered by parent category and time frame. The parent category in this case is theater and the time frame used is the months of the year. 
I used the "Convert Text to Columns Wizard" in order to separate the parent category from the subcategory, this wizard is located under the data tab in excel. The dates were presented in timestamp format, so I created a new column and converted the timestamp to human readable
format with the formula ` =(((date/60)/60/24)+DATE(1970,1,1))`. I also created a column with just the years by using the function `YEAR()`. Then I created a pivot table that shows the number of successful, failed, and canceled projects by months. The pivot table was sorted
in descending order to show successful outcome first. Lastly, a chart was created from the pivot table data to visualize the project outcomes by launch date. 

The results for the pivot table:

![PivotTable_Theater_Outcomes.PNG](/resources/PivotTable_Theater_Outcomes.PNG)

The results for the line chart:

![Theater_Outcomes_vs_Launch.png](/resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals

The analysis of outcomes based on goals was performed by collecting the outcome and goal data for the subcategory "plays". A table with dollar amount ranges was created and then I was able to use the `countifs()` function to populate each outcome based on
goal amount for "plays". The formula to sort the data in each range and outcome for plays includes criteria like so `=COUNTIFS(Sheet1!$D:$D,"<1000",Sheet1!$F:$F,"successful",Sheet1!$R:$R,"plays")`. 
This formula was repeated for each respective outcome and goal range. Then the total number of projects were calculated for each dollar amount range and from there I was able to use the `Round()` function to calculate each percentage of outcome. Once all percentages of successful, failed, and canceled outcomes were calculated for each goal range, I created a line chart from this table in order to visualize the data better. 

Table of ranges with percentages calculated:

![Table_Outcomes_vs_Goals.PNG](/resources/Table_Outcomes_vs_Goals.PNG)

Line chart showing the percentages of each range:

![Outcomes_vs_Goals.png](/resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered

I faced a challenge with a "#SPILL!" error when trying to convert the timestamp date to human readable format. 
The selection I was making was collecting cells with no data and resulted with seeing a "#SPILL!" and nothing else. I was able to overcome this challenge by
viewing the count of data in the launch date column and inserted it in my date conversion formula like this `=(((J$2:J$4115/60)/60/24)+DATE(1970,1,1))` so I would not have unnecessary output in the file.
 

## Results

-The first conclusion I can draw about the Outcomes based on Launch Date is that the Theater projects were the most successful when launched in May.
The second conclusion I can draw is that December has the lowest amount of Theater projects in total. The amount of successful and failed projects is about the same for the month of December.
-verall, it looks like there is a higher chance of success rate during the months of May - July.

-For the Outcomes based on Goals, I can conclude that play projects have a higher percentage of success when the fundraising goal is less than $4999.

-I believe a limitation of this dataset is the sample size is limited. There is also no measure of central tendency or spread. 
We can strengthen the report by adding statistical elements to deepen our analysis. We can create a table for goal amount that includes the 
mean, median, standard deviation and quartile ranges for each. Then we can create another table and calculate the same information for
pledge amount data. Once we have our calculations, we can create a box and whisker plot from the data of both tables to show any outliers.
