# MLB Fanbase Trends Analysis
### Link to the [project](https://public.tableau.com/app/profile/daniel.kim7933/viz/MLBFanbaseTrends/MLBFanbaseTrends?publish=yes)

## Motivation
The MLB Fanbase Trends Data Analysis project was derived from an experience I recently had where I was able to go to a Seattle Mariners game and was thrilled, as I have not been to a baseball game in years. When I arrived at T-Mobile Park, I was met with empty seats, sparse crowds, and an environment that had changed since my last visit when I was younger. I wanted to find what happened to the fanbase and analyze the trends, not for my Mariners, but for all the teams in MLB to discover what led to the difference I observed at my visit to the game.

## Project Overview
This project shows a full data pipeline from public APIs into an interactive Tableau dashboard that answers 7 core business questions about MLB Fanbase trends: fan engagement, geographic distribution, team growth, and social media reach across all 30 teams.

#### Key Findings:
- The New York Yankees' social media following of **16.2M is 3.6x** the league average
- The St.Louis Cardinals led all teams in Google Trends growth at **33%** year-over-year
- California is the only US state where two teams, the Dodgers and Giants, **tied at peak search interest**, reflecting one of MLB's most geographically dispersed fanbases

## Questions answered:
1. Which MLB teams have the largest fanbases?
2. How has fan engagement changed over time?
3. Which states generate the highest MLB interest?
4. Which teams are growing or declining in popularity?
5. What demographic or regional trends exist among MLB fans?
6. How do social media engagement metrics compare across teams?
7. Which teams have the strongest national vs local reach?

## Tech Stack
| Layer | Tool |
|-------|------|
| Data Collection | Python, MLB Stats API, Pytrends |
| Database | PostgreSQL |
| Data Transformation | SQL |
| Visualization | Tableau Public |

## Data Sources
| Source | Data | Table |
|-------|-------|-------|
| MLB Stats API | Teams, attendance 2021–2024 | teams, attendance |
| Google Trends (Pytrends) | Search interest by state + over time | fan_trends |
| Seeded estimates| Social media follwers by platform | social_media_metrics |

## Project Files
MLB_Project
- 01_setup_db.sql           ← Creates PostgreSQL schema and tables
- 02_etl_pipeline.py        ← Python ETL: pulls APIs and loads PostgreSQL
- 03_analytical_queries.sql ← Creates 9 analytical views for Tableau
- requirements.txt          ← Python dependencies
- README.md                 ← This file

## Dashboard Pages
Used the findings to build 5 interactive sheets in Tableau Public
- **Team Rankings**: a horizontal bar chart that ranks 30 teams by avg fan interest
- **Fan Interest Over Time**: a line chart with multiple lines showing national Google Trends by team
- **State Map**: a US map filled in by shades of fan interest score per state
- **Social Media**: a bar chart ranking teams by total followers across platforms
- **Team Growth**: a diverging bar chart that shows growth vs decline by team
