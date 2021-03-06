# Kickstarting with Excel

## Overview of Project

### Purpose

This project seeks to identify the factors that contribute to the success or failure of crowdfunding campaigns for theater projects. Analyzing data drawn from Kickstarter in Excel, I consider the impact of both launch dates and funding goals on the ultimate outcomes of these campaigns. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

The first factor I looked at was the launch date of theater campaigns. To identify the most favourable time of year to launch a new project, I first created a pivot table to display the number of successful, failed, and canceled campaigns for each month. Here is an image of the fields I selected to create the table:

![pivot fields](https://user-images.githubusercontent.com/79542537/110250321-b5d5e980-7f48-11eb-823d-cd340a9cd32e.png)

After creating the pivot table, I filtered Parent Category to show only theater campaigns, I filtered the column labels to exclude live campaigns, and I sorted the column labels in descending order, resulting in the following table:

![pivot_table](https://user-images.githubusercontent.com/79542537/110251237-a60cd400-7f4d-11eb-9c39-3d8986d6e20f.PNG)

Finally, I created the following line chart to visualize the results:

![Line chart](resources/Theater_Outcomes_vs_Launch.png)
### Analysis of Outcomes Based on Goals

The second part of my analysis looked at the relationship between funding goals and campaign success. To do this, I grouped campaign funding goals for theater campaigns into the following dollar-amount ranges:

![Goals](https://user-images.githubusercontent.com/79542537/111492627-36e46c00-8713-11eb-9965-d3b06d06e225.png)

Next, I used the =COUNTIFS function to get the number of successful, failed, and canceled theater campaigns for each dollar-amount range
For example, the following function displays the number of successful theater campaigns with goals between $1000 and $4999.

```
=COUNTIFS(Kickstarter!$D:$D,">999",Kickstarter!$D:$D,"<5000",Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays")
```
After obtaining the counts, I calculated the percentage of sucessful, failed, and canceled projects for each goal, producing the following results:

![Outcomes vs goals table](https://user-images.githubusercontent.com/79542537/111491362-2c75a280-8712-11eb-8f21-c03fb3a6bbc0.png)

Finally, I created a line chart of the results by selecting the Goal and Percentages columns:

![Line Chart](resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered

I completed this project without significant difficulties. The analysis of outcomes based on goals required inputting a number of functions to get the correct count for each outcome and dollar-amount range. It required careful proofing to ensure that the correct values were returned, and this task might be better accomplished by using scripting.

## Results

### What are two conclusions you can draw about the Outcomes based on Launch Date?

Visual inspection of the Outcomes based on Launch Date chart indicates that the success rate of theater campaigns clearly peaks in May. April and June are also quite favourable launch dates for theater projects. Secondly, the number of successful theater projects sharply declines toward the end of the year, reaching a low point in December.

### What can you conclude about the Outcomes based on Goals?

Theater campaigns that aim to raise less than $5000 are much more likely to succeed than projects with higher funding goals. Projects with goals of less than $5000 succeed more than 70% of the time. The success rate declines to 55% for projects between $5000 and $9999, and drops further as funding goals increase. There is a spike in the success rate for projects with goals between $35000 and $45000, but there was a only a small number of campaigns with goals that fell in this range.

### What are some limitations of this dataset?

#### Limited Number of Years in Dataset
Kickstarter is a relatively new platform, and the dataset can only provide information on a short period of time. There were only 26 theater campaigns launched on Kickstarter before 2014; the last month included in the dataset is February 2017. It is possible that trends for theater projects could change as the platform matures.

#### Lack of Geographic Information
The dataset indicates the country in which each campaign took place, but does not provide more detailed location information. This is important information for theater projects. Further data might help to determine if some markets are more favourable than others for crowdfunding plays.

#### First-Time Creators vs. Kickstarter Veterans
It would also be useful to know which Kickstarter campaigns have creators with previous experience running projects on the platform. The expected outcomes might be different for a first-time creator compared to that of a Kickstarter veteran. Further research on this question might help to calibrate the expectations for the client. 

### What are some other possible tables and/or graphs that we could create?

It might be useful to create a graph of outcomes based on campaign duration to determine if there is an optimal length of time for projects to be live on Kickstarter. Additionally, graphing the average donation size against the funding goal of successful campaigns could help to determine the ideal size of pledge levels. 
