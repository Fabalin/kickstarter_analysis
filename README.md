# Kickstarting with Excel

Analysis of Kickstarter Campagins to uncover trends to facilitate informed decision making of client's project goals. 

## Overview of Project

Kickstarter is a popular website to crowdsource funding for projects of all kinds. Projects can be categorized based on their nature, with examples ranging from technology to arts. Projects are funded by backers who contribute monitary funds towards the projects' goals. Client wishes to successfully crowdsource funding for her plays. Kickstarter Campagin data of projects ranging from the year 2009 to 2017 was analyzed to reveal the likelihood of success and failure of projects in the **theater** category. Microsoft Excel was used to perfom the analysis. 

### Purpose
Client's intial play titled *Fever* came close to its fundraising goal of $2,885 with a pledged amount equal to 85% of the goal, within a month. The client wishes to compare this experience with those of other projects to determine crucial paramters in their campagin strategy to successfully fund their future projects. These parameters, defined as **goal** and **launch date**, include the nominal amount of funding required, as well as the optimal time of campagin launch to esure successful funding.  

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
![Probability of Success And Failure of Theater Campagins based on Launch Date](https://github.com/Fabalin/kickstarter_analysis/blob/main/Theatre_Outcomes_vs_Launch.png)
The large dataset in Kickstarter was pivoted and drilled down to focus on the outcomes of the **theater** category. Globally, theater campagins are more successful than not, with a probability of 61.3% success and 36.1% failure. There are negligable amounts of canceled campagins throughout the year. 
![Descriptive Statistics of New Campagin Launches per Month](https://github.com/Fabalin/kickstarter_analysis/blob/main/Descriptive_Statistics_Total_Monthly_Launched_Campagins.png)
Additionally, the spread of new campagin launches have a relatively normal distribution with the mean being 114 campagins launched per month and the median being 113. There are more campagins launched during the summer (May-August) and less campagins launched during the winter (Nov-Jan). The total number of campagins launched for each of the months of May-August belong in the upper quartile whereas the total number of campagins launched for each of the winter months (Nov-December) belong in the lower quartile. May has the highest success rate of 67% whereas December is the nadir resting at 49% success rate.

### Analysis of Outcomes Based on Goals
![Percentage of Outcomes Based on Total Fundraising Goal Amounts](https://github.com/Fabalin/kickstarter_analysis/blob/main/Outcomes_vs_Goals.png)
This graph focuses on the **plays** subcategory wthin the **theater** category. Total number of campagins were counted, post-sorting based on criterias of outcomes and goals. the goals were further sectioned into brackets of 5000 with the cut offs of less than 1000 and more than 50,000. the COUNTIFS was used with the specifications:
'''
=COUNTIFS([range of outcomes], "outcome", [range of goals], "range of amount specified", [range of Subcategories], "plays")
'''
There were no canceled plays and the average success rate is 45.5%. The probability of successful play campagins decreases as the goal increases from less than 1000, up to 30,000 to 34,999. This steady decline exhibits a slight increase in slope at 5000 to 9999 and at 25,000 to 29,999. Following this, there is a reversal of the trend from 35,000 to 49,999. plays past 45,000 have little to no success rate. Highest success rate is observed at less than 1000 while lowest success rate is at 45,000 to 49,999.  

### Challenges and Difficulties Encountered
Depending on the processing speed and the RAM of your computer, the size of this dataset can prove challenging, especially when multiple pivot tables and extractions from the large data set were created in the same worksheet. While scrolling through the primary worksheet, the screen can often freeze. Closing and re-opening the excel file can solve this issue at times but limiting the amount of tabs and extra copies of the data and graphical summaries are the most effective. Additionally, the coding of the functions, specifically ones that reference data in other tabs can introduce errors in sampling if the correct data range is not selected. This is especially true when selecting the criterias for the COUNTIFS functions. Using proper syntax and debugging as well as performing QC on the functions employed can mitigate this issue. Improper sampling can also be introduced if the correct filters are not applied when analyzing the data. 

## Results

### Conclusions on Outcomes based on Launch Date
Based on the graphical summaries, the optimal time to launch a successful campagin is during the summer months, specifically around the month of May as it has the highest probability of success. Since client's first project *Fever* was launched during June to July, the quick funding can be explained by it coinciding with the optimal time of launch. Client should avoid launching theatrical campagins during the months of November to January as they experience the lowest rates of success. 

### Conclusions on Outcomes based on Goals
Client should aim to set the fundraising goal either around less than 1000 or 35,000 to 49,999 as the probability of success is mcuh greater than average. Client should avoid setting the goals to be between 25,000 to 34,999 or greater than 45,000 as the probability of failure far outpaces the probability of success. 

### Limitations of Dataset
The dataset must be further refined to have specifity regarding the country. In relation, the goal and pledged amounts are not standardized based on a singular currency. This could potentially shift some campagins to belong in different goal brackets and alter the data produced based on outcomes. Additionally market conditions can have impacts in backers' propensity towards funding. The analyzed data also does not take inflation into account as the projects are collected within a span of a decade. The conclusions made in this analysis can only apply within the specified categories as the results could be drastically different across categories. The data also does not take into acccount of the promotion of the campagin as well. 

### Other Possible Tables And/Or Graphs
Futher analysis of the relationship between the duration of the campagins along with their launch dates can be performed to determine the ideal campagin strategy. This can be done via three dimensional analysis summaried by a TSNE plot of the outcomes based on the launch date and campagin length. Similar line-plots comparing the differences between between the subcategories under the parent theater category to determine if the conclusions made based on outcomes and goals can be expanded upon to include the entirety of the theater category. 
