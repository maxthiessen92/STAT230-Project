# STAT230 project repository


## TITLE

Predicting the 2023 NHL All-Star Team

## PURPOSE

> Describe the general topic/phenomenon you want to study, as well some focused questions that you hope to answer and specific hypotheses that you intend to assess.

Every year, writers gather to pick the 2 best players of each position in the NHL to award the First Team or Second Team All Star accolade. With the current NHL season coming to an end I wanted to explore if I could predict what players would get these accolades through a logistic regression model.


## DATA

> Describe the dataset that you plan to use, with specifications of where it can be found (URL) and a short description.  (Eventually, you will probably want to combine data from multiple sources into one file. I will discuss data management techniques in the coming weeks, but for now you should simply list multiple sources if you have them.)

The data I'm planning to use is from [hockey-reference.com](https://www.hockey-reference.com/) which has a massive database of stats both new and old, team and individual based. I'm collecting the stats for every player that played in the [2021-22 season](https://www.hockey-reference.com/leagues/NHL_2022_skaters.html) for a training set, the players who won the [All-Star Team](https://www.hockey-reference.com/awards/nhl_all_star.html) honors, and the stats for every player that played in the [2022-23 season](https://www.hockey-reference.com/leagues/NHL_2023_skaters.html) as a testing set.

## POPULATION

> Specify what the observational units are (i.e., the rows of the data frame), describe the larger population/phenomenon to which you'll try to generalize, and (if appropriate) estimate roughly how many such individuals there are in the population.

The observational units are NHL players I'm trying to generalize to the current population of players playing in the league this 2022-23 season.

## RESPONSE VARIABLE

> What is the response variable? 

The response variable is whether the player is a first/second team all-star or not.

## EXPLANATORY VARIABLES

> Describe the variables that you'll examine for each observational unit (i.e., the columns of the data frame which correspond to a particular row). Carefully define each variable and describe how each was measured. For categorical variables, list the possible categories; for quantitative variables, specify the units of measurement. You may want to add more variables later on, but you should start with at least three explanatory variables (predictors).

The explanatory variables are as follows: points (pts) which represent the sum of goals and assists a player has. The more points you have the more exceptional you appear in the eyes of the writers voting. Point share (ps) which is a more advanced analytic that calculates how many points in the standings a player is responsible gain or losing for his team. A team gets 2 points for a win, 0 for a loss, and 1 for an overtime/shootout loss. If team ends the season with 100 points and a player has a point share of 8, the player is estimated to have accounted for 8 of the team's 100 points. Another explanatory variable is age. I believe that being either very young or very old will affect a player's overall season performance. The final variable I'm considering is player position. A defenseman doesn't have to be near the top of the league in points to get an all-star team selection. He usually just has to be near the top of the league in points AMONG DEFENSEMEN. Also only 2 of each position may be selected and I'm not sure exactly how to implement that into the model.

## Nick's comments

Your dataset is somewhat small, since the observational unit is team, no?
My concern is that your modeling will be constrained by this limitation and may be insufficient for what is needed for a STAT230 project.
Are there ways to explore individual level data?
Is there an equivalent of an "all-star team"? That might allow you to operate at the individual level.

Note that for each unit of observation, there will be clustering, since you are looking at repeated measures on the same unit (team or individual).
You can address this using something called "generalized estimating equations".
Can you please create a new issue on GitHub asking for more information on GEE's and I'd be glad to assist.

Once you address my query about individual vs. team characteristics I look forward to talking further (perhaps during my office hours on Thursday?).
