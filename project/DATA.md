---
layout: single
title: "Data"
permalink: /data/
sidebar:
  image: <img width="1543" height="1875" alt="Team-Vitality-Logo-Vector svg-" src="https://github.com/user-attachments/assets/b810f6f5-9120-48b8-8c93-7afc3573d0e5" />
  nav: "project"
published: true
---
## Data Sources
### Kaggle
Dataset providing a broad overview of competitive Counter-Strike, 2012-2026 ([link](https://www.kaggle.com/datasets/sergionefedov/counter-strike-competitive-scene-2012-2026?resource=download)).

### HLTV.org
*The* competitive Counter-Strike database. [Link](https://www.hltv.org/team/9565/vitality) to Team Vitality's page, [list](https://www.hltv.org/stats/teams/matches/9565/vitality?startDate=2026-01-01&endDate=2026-12-31) of map results from 2026, and each player's statistics page: [apEX](https://www.hltv.org/stats/players/7322/apex?csVersion=CS2), [ropz](https://www.hltv.org/stats/players/11816/ropz?csVersion=CS2), [ZywOo](https://www.hltv.org/stats/players/11893/zywoo?csVersion=CS2), [flameZ](https://www.hltv.org/stats/players/16693/flamez?csVersion=CS2), and [mezii](https://www.hltv.org/stats/players/18462/mezii?csVersion=CS2). 

### rdy.gg 
Visualizing Counter-Strike statistics, such as [player position](https://rdy.gg/en/cs2/stats?tab=player-positions), [player rating](https://rdy.gg/en/cs2/stats?tab=player-ratings), and [team summaries](https://rdy.gg/en/cs2/stats?tab=team-summary). 

## Data Cleaning
As far as cleaning goes, there isn't much to do. Since the data pulls directly from game match files, there are no NAs or rows left empty. However, there are still strings that need to be converted to integers and columns that should be implemented for easier data analysis. For example, in the `hltv/tournaments_2026.csv` Github file, the `Result` string was parsed into two separate integers, `Vitality Score` and  `Opponent Score` to form `hltv/tournaments_clean`. A `Differential` integer was also added to aid in visualizations. 

Before cleaning:

<img width="570" height="314" alt="image" src="https://github.com/user-attachments/assets/cef397df-f560-404f-bda8-4d33441ebbe4" />

After cleaning:

<img width="789" height="320" alt="image" src="https://github.com/user-attachments/assets/e792de46-416d-469e-aa9a-3c387e4bfaf5" />

## Data Visualization
