# Analysis-of-Kickstarter-Campaign
Dataset of Kickstarter Campaigns and Funding Goals

## Overview of Project

### Purpose
The purpose of this analysis is to know and compare how different compaigns progressed in terms of their funding goals vs their pledged and the time it took to achieve it. It is also to visualize and understand the campaign outcomes based on their funding goals and launch dates easily for those who are interested like Louise. In the process of this analysis,the skills in Excel that are used to analyze large sets of data thru use of sorting, filtering, using functions such as =ROUND(), =AVERAGAE(), and =COUNTIFS(), as well as using PivotTables, PivotCharts, and bar graphs for a more comprehensive look of the data is built on foundation.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
The first step to analyze the launch dates for theater campaigns is to create a pivot table on a separate worksheet to extract the information from the large data set. Excel creates the base automatically and lists all the columns of the dataset on the PivotTable Fields which makes it easier to filter and create the pivotTable based on what is to be analyzed. In this case, we're analyzing the outcomes based on launch dates. From the Fields section, drag down 'outcomes' to sections Columns and Values. Next, under Rows, drag down 'Date Created Conversion'. Then under Filters, drag down 'Parent Category' and 'Years'. It should look like this. <img width="294" alt="Screen Shot 2021-10-20 at 10 51 06 PM" src="https://user-images.githubusercontent.com/33046642/138203063-f93e4b7f-8afb-454d-a242-8d7ae04926c6.png">. Excel automatically populates the table. Next, filter 'Parent Category' to 'theater' and sort the Column Labels to only 'successful', 'failed', and 'canceled' outcomes. The table should look like this. <img width="331" alt="Screen Shot 2021-10-20 at 10 55 38 PM" src="https://user-images.githubusercontent.com/33046642/138203513-11be85c5-034b-4a84-bde5-33896dafeece.png">
Once, the table is filtered and sorted, insert a line chart with markers. Mine has numbers on the markers to visually tell the mark easily. The chart should look like this with the appropriate title. 
<img width="481" alt="Screen Shot 2021-10-20 at 11 05 30 PM" src="https://user-images.githubusercontent.com/33046642/138204491-72f9de96-8e0d-42b9-94a7-967d273682a0.png">
Off the bat, we can tell that May had the highest success (111) and highest failure (52)for theater campaign. Success declined after May making December have the least amount of campaigns. Failed outcome had a steady decline after May until it spiked up in October. For Canceled outcomes, the highest was in January but it looks rather steady throughout the year overall. There's not much change in the canceled outcomes compared to the successful and failed. 

### Analysis of Outcomes Based on Goals
For this step of the analysis, I started to manually create the table for the outcomes based on the funding goals of the theater campaigns with the following columns and rows labled as below:
<img width="757" alt="Screen Shot 2021-10-20 at 11 47 14 PM" src="https://user-images.githubusercontent.com/33046642/138208163-403f8e16-cc25-4871-97f6-fbe99e828836.png">
Next, I used the COUNTIFS() function for the cells with the conditions that each cell met the 'Goal' for each row and the 'Outcome' for each column as well as the subcategory 'plays' called from the Kickstarter worksheet. I copy-pasted the formula for all and only had to change the 'Goal' and 'Outcome'. A sample of the formula is shown below for the first two columns and first two goals:
         For successful outcome and goal less than 1000: 
      '=COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays")'
         For failed outcome and goal 1000 to 4999:           '=COUNTIFS(Kickstarter!$D:$D,">=1000",Kickstarter!$F:$F,"failed",Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,"<=4999")'
The table should look like this:<img width="382" alt="Screen Shot 2021-10-21 at 12 41 46 AM" src="https://user-images.githubusercontent.com/33046642/138212744-9f09c095-2587-4bf2-a725-0cabcad4ab74.png">
Then, in cell E2 for Total Projects, I used the SUM() function. 

        
        

### Challenges and Difficulties Encountered
One of the challenges that I encountered was using the COUNTIFS() for the Deliverable 2 portion of this assignment. The total count of successful, failed, and canceled for each goal (row) was 1 off. I have double checked on the Kickstarter sheet, filtered on the 'outcomes', 'goal' and 'subcategory' for each and it did not match. I've also checked to see if I wrote the function properly, retyped it on a new sheet, and eventually asked for help from the Learning Assistant. They've also encountered the same issue as I did and told me to ignore the count(off by 1) and resume what I'm doing. Another small challenge was when I made the pivot table for 'Outcomes Based on Launch Date' and the 'Year' column did not populate under the fields. After some trial and error, I found that selecting on the 'Change Data Source' under 'PivotTable Analyze' tab allowed me to extend the original table instead of having to create a whole new table and worksheet again.

## Results

- What are two conclusions you can draw about the Theater Outcomes based on Launch Date?
May and June had the highest amount of successful campaigns which means that early summer is the best time for Louise to run a theater campaign and that the winter months, more specifically December, are not the most ideal. For month of December, I assume less is donated to campaigns since its the holiday season and people are spending their money more on gifts and other materials than donating to theater. The theater category also had the least amount of canceled campaigns throughout the whole year. 

- What can you conclude about the Outcomes based on Goals?
Goals that are more reasonable attainable, for instance, less than $1000, are more likely to be successful than a unrealistic, rather more expensive, goal like more than $40,000. A goal that's less than a $1000 would mean that the average of donations would also be less but more people are willing to donate a few cents than a few dollars. Unless you're just super rich, but that would be considered an outlier in the data. Likewise, the higher the goal amount, the more likely it is to fail due to few or no pledges, in other words, people have to donate more money on average. 

- What are some limitations of this dataset?
Organization. More data information may mean more precise and accurate analysis, but also prone to looking 'messy' and overwhelming which could or may hinder the quality if not managed or organized. 

- What are some other possible tables and/or graphs that we could create?
We could use pie charts/bar graph to see which categories or subcategories are more popular filtered by the successful. A line graph for each subcategory to see the trends for each year. 
If Louisa wasn't just interested in the plays/theater category, we could also create a pivot table to see what were the top 3 categories by the amount of successful campaigns. 
