# 2018-2022 Household Income & Housing Market Analysis

### _What does income distribution look like in neighborhoods impacted by government policies?_
---

#### Introduction
In this project, I examined median house sales and household income data in 12 metropolitan areas across the US from 2018 to 2022 to understand how housing prices affect Americans across various income levels. The metropolitan areas selected for analysis, have been identified by the Department of Housing and Urban Development (HUD) as regions that could benefit from expanded homeownership opportunities. Recent events, as of 2024, like the initiative to issue a tax credit for first-time homebuyers that meet certain criteria, sparked my interest in understanding the housing market through data analysis. As a result, this project is purely for informational purposes.  

#### Background
Revitalization Areas, designated by HUD, are geographic locations identified as areas that could benefit from increased homeownership opportunities. To facilitate this, HUD offers special programs like the Good Neighbor Next Door Program (GNND) to eligible professionals within these areas. As a result, the median household income data provided in the dataset includes income from rent-controlled citizens, law enforcement professionals, emergency responders, and teachers residing in the communities they serve. 

#### Objective
My objective was to combine various data processing techniques using Excel, SQL querying, and a visualization tool like Tableau to explore the relationship between household income and median sales price across US regions down to the neighborhood level.

##### Here are a few questions I set out to answer:

1. Which state and metro area has the most revitalization areas?
2. Does the unemployment rate have an influence on median house sales price?
3. What metro areas have the highest median sales price?
4. Which metro region has the highest number of working professionals making more than 150k?
5. What does income distribution look like within the following counties?


##### Key Insights

1. CA, TX, NY/NJ, and FL had the most households living in revitalization areas representing 43% of the population within the dataset.
2. From the results, I concluded the unemployment rate did not directly influence the price of median house sales.
3. San Jose Sunnyvale Santa Clara (85) had the highest median sales price at $1.625 million in 2022.
4. San Jose Sunnyvale Santa Clara (85) had the highest number of working professionals making over 151k+. 
5. Income distribution across 4 various counties shows the majority of income levels within 0-75k.

#### The Data

This project uses (3) sources to provide information: the [Housing Urban Department’s (HUD) Revitalization Areas](https://catalog.data.gov/dataset/revitalization-areas), Zillow’s Housing data, and the BLS unemployment rate.

The dataset was formatted, cleaned, and compiled individually and represents 4 years (2018 – 2022) of housing market trends in 12 metropolitan regions across the US.
 
There were 220,109 households included in the HUD dataset. To account for missing values, only 220,017 households were used. In this dataset, 52 States were observed with Puerto Rico and Washington DC identified as States.
 
The [Zillow Housing Dataset](https://www.zillow.com/research/data/) contained median home sales for the 4 states and their counties shown in the HUD dataset. 

The [BLS Unemployment Rate Dataset](https://www.bls.gov/) contained the average yearly unemployment rate for the 4 states and their counties shown in the HUD dataset.

### The key variables used from the HUD Revitalization Areas Dataset are:
* Sur Area Name – Metropolitan Area Name
* State
* County
* BlkGrp - Block Group
* Medhhinc - Median Household Income

### The key variables used from the Zillow Single Family Home Dataset are:
* Median House Sales Price
* Year
* Region Name
* State Code
* Municipal Code

### The key variables used from the BLS Unemployment Dataset are:
* Unemployment Rate
* State FIPS Code
* Year

_Tools used:_
Excel, SQL querying and Tableau

#### The Analysis + Commentary
_Which state and metro area has the most revitalization counties in the HUD dataset?_

I answered this question by doing a quick pivot table analysis in Excel. From the table, I found 4 states representing 43% of the households living in revitalization counties – 6(CA), 48(TX) 36(NY/NJ), and 12(FL).  
<img src="images/HUD Pivot Table 1.png">

I filtered the top 4 states to further explore the median household incomes at the county and metro area levels.

To do this, I used the following SQL query which provided the top 5 counties within each state and the number of households shown within the counties.

<img src="images/HUD SQL Code.png"/>

The results showed the top 5 counties in the 4 states above ranked by the number of households within each county. For example, TX (labeled as 48) showed counties 201(Harris), 113(Dallas), 439(Tarrant), 29(Bexar), and 453(Travis) to have the most households.

<img src="images/HUD SQL Results.png"/>
 
_Does the unemployment rate have an influence on median house sales price?_

To answer this question, I visualized the Zillow Housing data along with the BLS unemployment rate data using the following line chart. The line chart represents the 12 metro areas’ total median household income and the average unemployment rate in these areas from 2018-2022.

<img src="images/HUD Chart Unemployment.png"/>

The results show a steady increase in median house sales prices between 2018 to 2019 as the unemployment rate decreased. However, between 2020 and 2021, median house sales prices surged up to 22.4% surpassing previous years’ median house sales by 18%. From the results, I concluded the unemployment rate did not influence the price of median house sales. Further analysis would be needed to see what other factors could be influencing the median house sales price.

[Click here to use interactive chart](https://public.tableau.com/shared/KKHRF9WFQ?:display_count=n&:origin=viz_share_link)

_What metro areas have the highest median sales price?_

Continuing with the Zillow Housing dataset, I dived deeper to see which counties had the highest median sales price by their metropolitan region.  San Jose Sunnyvale Santa Clara County (85) had the highest median sales at $1.625 million in 2022. San Jose Sunnyvale Santa Clara County trends upward as an outlier with generally higher incomes compared to the remaining regions in the chart. Los Angeles County (37) median house sales price follows right below Sunnyvale Santa Clara with $1.074 million. 

<img src="images/HUD Counties Chart 1.png"/>

[Click here to use interactive chart](https://public.tableau.com/shared/WSCYR2D4H?:display_count=n&:origin=viz_share_link)

_What does income distribution look like within the following counties?_

To answer this question, I compared the income distribution of the 2 counties with a median sales price above $1 million and the 2 counties with a median sales price below $300,000. Since one county can have up to nine block groups, I looked at the income distribution across the block groups in the county that had more than one income level present. The heat map below shows Santa Clara County’s Block ID-3 with 18% of the total Block Group having median income levels between 101-150k. Whereas Dallas County showed 27% of households having a median income between 26-50k. Thus, comparing median household income between block groups shows locations where the income distribution levels could be improved.

<img src="images/Tree map.png"/>

[Click here to use interactive chart](https://public.tableau.com/views/2022-23NBASeasonPlayerTeamAnalysisDashboard/ScatterPlot?:language=en-US&:display_count=n&:origin=viz_share_link)


[Click here to use interactive chart](https://public.tableau.com/views/2022-23NBASeasonPlayerTeamAnalysisDashboard/Treemap?:language=en-US&:display_count=n&:origin=viz_share_link)

#### Insights and Recommendations
Given that the median household income data in the dataset primarily represent rent-controlled citizens and working-class professionals such as law enforcement, emergency responders, and teachers residing in their respective communities, I would advise policymakers to maintain their focus on implementing policies aimed at improving the distribution of median household income across neighborhood block groups. Additionally, I would recommend further analysis of the unemployment rate to identify which occupations and income levels are most affected, enabling policymakers to target interventions more effectively. If you  enjoyed reading my analysis and are interested in knowing more, please feel free to connect with me on LinkedIn and check out my other projects!
