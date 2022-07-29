# Predicting Why a Pro Valorant eSports Team Wins
This project used competitive Valorant data to determine if a competitive team would win based on a selection of features. This dataset came from roughly 15,000 completed matches and a mix of professional and amateur teams.

# ![Valorant Logo](https://docs.google.com/drawings/d/e/2PACX-1vToimVURVg6RLxixVNdCNNn5MFUikhiRf7SrACWlY1XuZzvcBiD5OjgfuZlJkEiIoBLOSL2-DhfwPmg/pub?w=584&h=150 "Valorant Logo")

Image Source: [Valorant Asset Kit](https://playvalorant.com/en-us/news/game-updates/valorant-asset-kit/)

## About Valorant
Valorant is a Free-to-Play 5v5 character-based, tactical First-Person-Shooter game developed by Riot Games and released in 2021. Every player starts with a pistol and one ability to use every round, they need to purchase other weapons or abilities from money earned the prior round. Purchases carry over to the next round if the player does not die. Teams take turns being on either attack or defend, spending 12 rounds on each. The first team to win 13 round is the winner. If both teams are at 12, then an overtime occurs with teams getting a set economy each round, they alternate sides after every round, and a team has to win by 2 rounds to win the match in overtime.

More information can be found on the PlayValorant.com [website](https://playvalorant.com/en-us/).

## Data:

The data originally came from a Kaggle search where I ended on this [page]([https://playvalorant.com/en-us/news/game-updates/valorant-asset-kit/](https://www.kaggle.com/datasets/visualize25/valorant-pro-matches-full-data)). A CSV file of the data can be downloaded [here](https://docs.google.com/spreadsheets/d/e/2PACX-1vRgfbORLFSODzyC5OGp0BWGWJ8VD7Vcx9DkjxBdnSgzfjxJmqAXlk-iyb8e6io3dYkjUCWtZuteOIZY/pub?output=csv).

## Author:
Clint Atterberry

## email:
onedayzero@gmail.com

## linkedin:
[Link to profile](https://www.linkedin.com/in/clintatterberry/)

# Data Dictionary
|Variable Name|Description|
|---|---|
|GameID|Identifier Variable|
|MatchID|Identifier Variable|
|Map|The map that the match was played on|
|Team1ID|Identifier Variable/Unique to eam|
|Team2ID|Identifier Variable/Unique to team|
|Team1|The name of team 1, they have map selection|
|Team2|The name of team 2, they have side selection (attack or defend)|
|Winner|The team that won the match|
|Team1_TotalRounds|How many rounds did team 1 win|
|Team2_TotalRounds|How many rounds did team 2 win|
|Team1_SideFirstHalf|Did team 1 attack or defend in the first half|
|Team2_SideFirstHalf|Did team 1 attack or defend in the first half|
|Team1_RoundsFirstHalf|How many rounds team 1 won in the first half|
|Team1_RoundsSecondtHalf|How many rounds team 1 won in the second half|
|Team1_RoundsOT|How many rounds team 1 won in overtime|
|Team2_RoundsFirstHalf|How many rounds team 2 won in the first half|
|Team2_RoundsSecondtHalf|How many rounds team 2 won in the second half|
|Team2_RoundsOT|How many rounds team 2 won in overtime|
|Team1_PistolWon|How many pistol rounds team 1 won|
|Team1_Eco|How many rounds team 1 spent a small portion of their eco|
|Team1_EcoWon|How many eco rounds team 1 won|
|Team1_SemiEco|How many rounds team 1 spent a moderate portion of their eco|
|Team1_SemiEcoWon|How many semieco rounds team 1 won|
|Team1_SemiBuy|How many rounds team 1 spent a large portion of their eco|
|Team1_SemiBuyWon|How many semibuy rounds team 1 won|
|Team1_FullBuy|How many rounds team 1 spent enough for full loadouts|
|Team1_FullBuyWon|How many fullbuy rounds team 1 won|
|Team2_PistolWon|How many pistol rounds team 2 won|
|Team2_Eco|How many rounds team 2 spent a small portion of their eco|
|Team2_EcoWon|How many eco rounds team 2 won|
|Team2_SemiEco|How many rounds team 2 spent a moderate portion of their eco|
|Team2_SemiEcoWon|How many semieco rounds team 2 won|
|Team2_SemiBuy|How many rounds team 2 spent a large portion of their eco|
|Team2_SemiBuyWon|How many semibuy rounds team 2 won|
|Team2_FullBuy|How many rounds team 2 spent enough for full loadouts|
|Team2_FullBuyWon|How many fullbuy rounds team 2 won|
|Team1_Won|Did team 1 win the match|

# Overview of Project
This project was completed using Google Colab notebook. Data was cleaned, analyzed, prepared, then modeled using various machine learning methods. The data was first explored with minimal changes, only unnecessary columns were dropped. Later, feature engineering was done to limit the scope of the models to make predictions based off of much fewer features. The features kept were: Map, Team1_SideFirstHalf, Team1_RuondsFirstHalf, Team1_PistolWon, Team1_FullBuyWon, and Team1_Won.


## Insights
### ![Map Distribution](https://docs.google.com/drawings/d/e/2PACX-1vRcI1mLr5gXf73vxudpurtan8YcsRvHkV6s-V9diZfXOrqI-e4XyASMfmtIVAqtPWfNEgi_T8iWrHwF/pub?w=391&h=262)

Above is a graph that shows the distribution of maps in the dataset. The lowest maps are ones that are newer and were not available during part of the data collection. After exploration of the data, there is little to no variance outside of the newest one, which has the most variance but has the smallest sample size.

### ![Pistol Wins vs Full Buy Wins](https://docs.google.com/drawings/d/e/2PACX-1vQ4MA-m39ryjvvml3lNF4XbsPHJ2L6knqV5Ls7mrLW07TsE3-DADWhPAJsI_uWnO1sicVzLiZzVTftD/pub?w=379&h=264)
Above is a graph that shows the connection between how many of the pistol rounds team 1 wins (0, 1, or 2) and how many of the full buy rounds they win. The pistol The mean data is fairly similar; however, there is a lot more variance when team 1 does not when either pistol round. There is very little difference whether or not team 1 started on attack or defend.

### ![Pistol Wins vs First Half Wins by Map](https://docs.google.com/drawings/d/e/2PACX-1vQ3oDb6shrJA2kB51jMcmPgp39Plb1SVBBrLicpg5dDcEltbIeT67RdTLR6Xoikxa7mh4jRCCb3w-Zi/pub?w=553&h=394)
Above is a graph that has 3 variables, pistol wins, rounds won during the first half, and on what map these statistics occured. The interesting statistic is not the variance on the map 'Fracture', that is a new map and is expected, but when a team does not win their pistol round (there is one per half so if they won 0 they lost the round in the first half) they still will usually win around 6 rounds out of 12. This value changes to 8 out of 12 rounds if they won the first round and preceeded to win the first round of the second half, so they would be 9 out of 13 rounds won.

### ![Type I and Type II Error Matrix](https://docs.google.com/drawings/d/e/2PACX-1vQC_RFtSCesXmJ2tKeOZG4Km1TTLgRR5FAkG5worxbhziHU3HJV6r8ga4DAbDmM9t2rrMjzy9A4mFQ6/pub?w=384&h=282)


## Summary

## Recommendations
