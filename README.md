# Kickstarting with Excel
## Overview of Project
### Purpose

To help deciding successful factors to meet fundraising goal for different campaigns by their launch date and funding range with charts and pivot tables created using main dataset **Kickstarter**

## Analysis and Challanges
### Analysis of Outcomes Based on Launch Date

Considering below dataset for all categories based on **"Launch Date"**, we can observe that successful outcomes are average 50%, failed outcomes are 38% and canceled outcomes are average 10% of total outcomes thru out the year. Almost same number of campaigns are launches thru out the years for each month. This data represents very steady observations. 

![OutcomesbyLaunchDate](https://user-images.githubusercontent.com/107717882/174674129-dda919df-7356-4680-a2e6-a6bf8ab51e4c.png)

Considering below dataset specifically for "theater" parent category, we can see that May and June show highest successful outcomes as well as highest failed outcomes. Here also data are steady, if we calculate more, the average percentage of successful (60%), failed (36%), canceled (3%) are same throughout the year for all years based on **"Launched Date"**.

![TheaterOutcomesbyLaunchDate](https://user-images.githubusercontent.com/107717882/174674320-af34d2b9-46bf-428e-a284-9b4a428676c0.png)

Graph is also having very steady lines except May, June and July showing spikes in *"successful"* outcomes. 

![Theater_Outcomes_vs_Launch ](https://user-images.githubusercontent.com/107717882/174674733-7ca151b1-8e10-4673-bb17-7927a70a6e4e.png)

### Analysis of Outcomes Based on Goals
From below dataset figure we can see that most of the successful and failed plays fall between range 0 to 10000 of goals as highest plays are introduced in this range. Surprisingly or fortunately, there is no single canceled play is between whole range of Goal.  Also, very few projects introduced above range 25000. Highest successful percentage of total plays fall in below 1000 range, and highest failed percentage of total plays fall in range between 45000 to 49999. Overall, percentage for successful plays are decreasing as goal increase and percentage of failed plays are increasing as goal increases. There are exceptional observations are there which disobey this trend in range from 35000 to 45000. 

![OutcomesBasedonGoals](https://user-images.githubusercontent.com/107717882/174674789-38c633b7-441a-497b-9c8c-e06c1c254428.png)

Here chart is representing very interesting pattern, as range increases, percentage successful line graph decreases and percentage of failed line graph increases.

![Outcomes_vs_Goals](https://user-images.githubusercontent.com/107717882/174674851-cc0f92a2-2918-42dd-8114-8f8ff53f5496.png)

Also, standard deviation for both percentage of successful plays (31.5) and percentage of failed plays(32) are same that indicates data distributions are almost same for given ranges mostly in opposite directions, three times they are almost same as lines crossed each other. 

### Challanges and Difficulties Encountered

The **"Outcomes Based on Launch Date"** is quite easy and simple analysis as it represents almost equal data distribution for all outcomes thru out year. Pivot table and chart creation are simple and useful to understand campaigns launched vs successful/failed/canceled.

The **"Outcome Based on Goals"** is very interesting analysis as we have introduced "Goal" ranges. Here, the final dataset must contain only 8 columns so using only Goal column its little difficult for me to perform COUNTSIF () function to count number of successful, failed and canceled outcomes. I used few formulas to find substrings and convert them into value to compare. For ex. for 1000 to 4999 row in Goal column, I used LEFT () with FIND to get first word in string (1000) and convert it into number by using VALUE (). To find last word (4999) I used RIGHT () with SUBSTITUTE (), REP () and finally trin it with TRIM ().
Real difficulty is; you cannot convert “Less” and “More” into value so I put code in IFERROR () and provide 0 for greater than comparison and “100000000” (I wanted to apply MAX () to find maximum Goal but somehow it gives me error).

## Results
- Two conclusions are made about the **Theater Outcomes by Launch Date**
  1.	No campaign has been canceled for category “theater” in October.
  2.	The highest number of successful campaigns are launched in May for “theater” category are 111. 
- One conclusion is made about the **Outcomes based on Goals**
  1.	As goal ranges increases percentage of successful outcomes are decreasing and percentage of failed outcomes increases.

- **Summary of the limitations of the dataset**

  The dataset **“Theater Outcomes by Launch Date”** represents very steady data in nature for all months/years for all categories. We cannot say much in detail from that data to help deciding future steps
The column “Goal” which represents goal ranges in “Outcomes Based on Goals” is little difficult to get comparing ranges for COUNTIFS () function in Excel.  

- **Recommendation for additional tables or graphs**

  For **“Theater Outcomes by Launch Date”** dataset we can add “Subcategory” as one more filter to analyze more. Also, another pivot table using “successful” outcomes as   column with “Goals” and “Pledged” columns gives more idea about successful campaigns. We can do same for “failed” and “canceled” outcomes.














