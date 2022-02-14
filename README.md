# Module 1: Kickstarter
Theatre Funding Comparison 
Introduction
	The purpose of this analysis was to help Louise, understand how different fundraisers created by theatres to help fund plays performed. Having knowledge on performance of fundraisers based on their initial goals and the timing of launch helps us understand the best time period fundraise and the best budget to create for a play to stay successful. 
Process and Challenges 
	We started of our analysis by splitting it into two parts. Analysis of the outcome of fundraisers based on the launch date and based on the total funding goal. When looking at the data set provided, we notice our first challenge. The launch date data was in Unix timestamp, which is a counting number that counts seconds past 1970. To help us use the data to our advantage, we use the following formula.

“Date Created Conversion” =(((J#/60)/60)/24)+DATE(1970,1,1)

	This formula helps convert the Unix timestamp into a MM/DD/YY format by changing seconds into minutes, minutes into hours, hours into days, and then adding it to the January 1, 1970, which is the starting ticker for Unix. We named this variable “Date Created Conversion”. Using this new variable, we created a new variable known as “Year” to help organize our data. The formula used was as follows.

“Year” =YEAR(Q#)

	Using our new created variables, we can create a pivot table showing us the amount of successful, failed, and canceled fundraisers by month. To do this we created a pivot table with Launch dates grouped by months (Date created conversion) as the rows, outcomes as the columns, the data/values as the count of each outcome category and filtered by categories to allow us to only see theater fundraisers. Using this preset we were able to obtain the following pivot table. 

Count of outcome	Column Labels			
Row Labels	successful	failed	canceled	Grand Total
Jan	56	33	7	96
Feb	71	39	3	113
Mar	56	33	3	92
Apr	71	40	2	113
May	111	52	3	166
Jun	100	49	4	153
Jul	87	50	1	138
Aug	72	47	4	123
Sep	59	34	4	97
Oct	65	50		115
Nov	54	31	3	88
Dec	37	35	3	75
Grand Total	839	493	37	1369

	Using this pivot table, we were able to create a line graph resembling the amount of successful, failed, and canceled theater fundraisers based on launch date. The graph can be found in the results section of this paper. 
	The next analysis we wanted to cover was the result of outcomes based on the amount their goal was. We are able to leverage this by creating a formula that counts a certain fundraiser based on if they meet certain criteria. For example, if we wanted to count the number of fundraisers that wanted to earn less than 1000, was successful, and was fundraising for a play we would use the following formula. 

=COUNTIFS(Kickstarter!$F$2:$F$4115,"Successful",Kickstarter!$D$2:$D$4115, "<1000",Kickstarter!$O$2:$O$4115, "plays")

	Duplicating this formula and adjusting for other criteria we were able to create a full table resembling the amounts of successful, failed, and canceled play fundraisers by their goals of increments of 5000. Using this data we calculated the total amount of projects per goal bracket and divided outcomes by the total to find the percentage distribution of outcomes. Here is our graph.
Goal	Number Successful	Number Failed	Number Canceled	Total Projects	Percentage Successful	Percentage Failed	Percentage Canceled
Less Than 1000	141	45	0	186	0.758064516	0.241935484	0
1000 to 4999	388	146	0	534	0.72659176	0.27340824	0
5000 to 9999	93	76	0	169	0.550295858	0.449704142	0
10000 to 14999	39	33	0	72	0.541666667	0.458333333	0
15000 to 19999	12	12	0	24	0.5	0.5	0
20000 to 24999	9	11	0	20	0.45	0.55	0
25000 to 29999	1	4	0	5	0.2	0.8	0
30000 to 34999	3	8	0	11	0.272727273	0.727272727	0
35000 to 39999	4	2	0	6	0.666666667	0.333333333	0
40000 to 44999	2	1	0	3	0.666666667	0.333333333	0
45000 to 49999	0	1	0	1	0	1	0
50000 or More	2	14	0	16	0.125	0.875	0

Using this graph we created a line chart that resembles percentage of each outcomes based on the volume of their goals. This can be found in the results section of this paper. 
Results 
The first data set we are going to look at is our data based on launch date.
 
	Here we can find two conclusions based on our line graph, during May you have both the greatest number of fundraisers created and the greatest number of successful fundraisers. Meaning said, we should have our fundraiser during the month of May, although having one of the highest failed numbers, it has the highest success rate. 
On the other hand, lets look at the following line graph that shows us the percentage of fundraisers that were successful, failed, or canceled based on their goals. 
 
	Based on this graph, we can conclude that the lower your goals are, the higher your likelihood of successfully accomplishing your goals may be. Although there are some thins to note. At higher goal amounts, we may have skewed numbers due to a lack of data with ranges such as 45,000 to 49,999 having only 1 fundraiser. This inconsistency may lead to our data being inaccurately represented. From goals 0 to 25,000 where we do have reliable data, we can see that overall, the higher goal amounts result in lower success rates. 
	One of the few downfalls I see in the graphs created is that we purely rely on the launch date and outcomes. Instead, it would be beneficial to incorporate a third factor, length of fundraiser which could be found by finding the difference between deadline and launch date. This would allow us to see if the length of time a fundraiser took affected the success rate of a given fundraiser by creating a “goal per day” variable. Unlike the total goal variable we used in our current data, using a goal per day variable will put different fundraisers in equal footing, therefore giving us a more accurate representation of what you should set as your goal depending on the timeframe you have to raise money.  



