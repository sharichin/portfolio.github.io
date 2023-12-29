# 2022-23 NBA Season Player and Team Analysis

### How does the number of minutes played in a season affect the number of points scored?
---
<div class='tableauPlaceholder' id='viz1703810253062' style='position: relative'><noscript><a href='#'><img alt=' ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;20&#47;2022-23NBASeasonPlayerTeamAnalysisDashboard&#47;22-23NBATeamAnalysisDashboard&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='2022-23NBASeasonPlayerTeamAnalysisDashboard&#47;22-23NBATeamAnalysisDashboard' /><param name='tabs' value='yes' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;20&#47;2022-23NBASeasonPlayerTeamAnalysisDashboard&#47;22-23NBATeamAnalysisDashboard&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1703810253062');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.minWidth='1366px';vizElement.style.maxWidth='100%';vizElement.style.minHeight='818px';vizElement.style.maxHeight=(divElement.offsetWidth*0.75)+'px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.minWidth='1366px';vizElement.style.maxWidth='100%';vizElement.style.minHeight='818px';vizElement.style.maxHeight=(divElement.offsetWidth*0.75)+'px';} else { vizElement.style.width='100%';vizElement.style.minHeight='1400px';vizElement.style.maxHeight=(divElement.offsetWidth*1.77)+'px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>

#### Introduction
I enjoy playing and watching soccer and track, so I chose to add a sports project to my portfolio. For this project, I analyzed basketball players' individual and team performance from the 2022-2023 NBA Season. Since the data included both player and team statistics, I explored the details to identify areas players and teams could potentially improve in. Also in my analysis, I chose to highlight 4 teams (MIA, ATL, POR, GSW) to showcase teams from the East and West coast in cities I've had the opportunity to experience and live in. 

#### Objective
I've been asked to provide statistics on player's performance and the teams they play on.

Here are a few questions I set out to answer:
1 - What position is most efficient at shooting 3-pointers for each team?
2 - Does the number of minutes played relate to the total number of points made in a season?
3 - What were the total points for each team and how much did each player contribute? Portland?
4 - What players had the most assists in every position?
5 - Use a player's points assists, and total rebounds to find how individual players performed during the season.


#### Key Insights
1 - Shooting guard is the most efficient position at shooting 3-pointers for each team, with 5 of 30 teams ranking in the top quartile.
2 - 91% of the variation in the number of points a player has in the season is related to the total number of minutes played.
3 - SAC has 9,898 points which is 145 points more than GSW, the second-best team.
4 – Point guard Russel Westbrook has 2.5 times more assists than the shooting guard position’s top number of assist.
5 - Atlanta’s Trae Young is a clear outlier with 741 assists, 1914 points and 217 rebounds.

#### The Data
Using Tableau, I analyzed player and team statistics to identify areas players and teams could improve in from the beginning of the season, October 2022 to the championship game, April 2023. The data contains 30 teams with 5 different positions and 539 different players. Although 31 attributes were included in the data dictionary, only the following 9 were used in this analysis.

The data included the following:
•	Tm - Team
•	Pos - Position
•	Player Name
•	MP - Minutes Played
•	3P - 3-Pointers Made
•	3PA - 3-Pointers Made
•	TRB - Total Rebounds
•	AST - Assists
•	PTS - Total Points Scored

#### The Analysis + Commentary
What position is most efficient at shooting 3-pointers for each team?

<img src="images/Low Grad Percent Rate Bar Chart.png" alt="Bar Chart showing low graduation rate" width="700" height="700">

To answer the question above, I created a heatmap to show the teams with the highest 3-point average split by positions. The heat map shows 5 of the 30 teams (MEM, LAC, PHI, DEN, and MIL) to have 40.3% to 42.6% shooting average for the shooting guard position. The next best position would be Center position showing 3 teams with an average 3-point shot from 41.1% to 46.2%. As a result, the shooting guard position is the most efficient position at shooting 3-point shots for each team. 

<img src="images/Avg Class Size vs Attending College Scatter Plot.png"/>
Does the number of minutes played relate to the total number of points made in a season?

I explored the data further to find if there was a relationship between the number of minutes a player played in the season and the total number of points scored. To do this, I created a scatter plot and drew a trend line using linear regression. Because I knew the total number of points started at the beginning of the season when the first game was played, I forced the y-intercept regression line to start at 0; so, the estimated value of the points when no minutes were played would be 0.

The trendline showed the R-squared value to be 0.912 and the slope to be 0.497. This indicates that 91.2% of the variation in the total number of points made in the season is related to the number of minutes played in the season. The slope also indicates that for each additional minute played the number of points is expected to increase by approximately 49.7%. It was interesting to see this analysis. The data shows a strong positive relationship between the number of minutes played and the total number of points made in a season. Further analysis would be needed to find other relationships and factors that contribute to a player’s total points scored. 

<img src="images/Avg Passing 4th Grade Math Line Chart.png"/>
What were the total points for each team and how much did each player contribute?

To find this, I created a stacked bar chart showing the total number of points per team stacked by players’ total points within the team in descending order from highest to lowest. SAC for instance has 9,898 points which is 145 points more than GSW, the second-best team. The gradual narrowing of the column size shows the player’s points within the total points scored by the team. BOS’s Jayson Tatum has the most points scored out of Boston and overall with 2,225 points in the season.  

What players had the most assists in every position?
I chose to answer the question above by using a tree map showing the 5 different positions grouped into larger squares, and within the larger squares are players’ total number of assists. For the Point Guard position and overall positions, Russel Westbrook has 2.5 times more assists compared to the Shooting Guard position’s top number of assists. 

Use a player's points assists, and total rebounds to find how individual players performed during the season.
To answer the following question above, I chose to highlight a few teams from the East and West coast. I created a bubble plot to show the total number of points, assists, and rebounds (indicated by the size of the players' bubble) for East Coast teams, MIA, ATL, and West Coast teams POR, GSW.  Atlanta’s Trae Young is a clear outlier with 741 assists, 1914 points and 217 rebounds. 

#### Insights and Recommendations
I enjoyed exploring the 22-23 NBA season and there are a lot of insights to take away from this analysis. If you  enjoyed reading my analysis and are interested in knowing more, please feel free to connect with me on LinkedIn and check out my other projects!
