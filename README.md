# Fantasy-Premier-League
HACK KU 2021- Done by M. Atif Siddiqui and Fares Nael

## API for dataset
url = 'https://fantasy.premierleague.com/api/bootstrap-static/'

## What is Fantasy-Premier-League
My friend Fares and I have been playing the Official Fanatsy English Premier League for a few years now. But we have failed to pick the winning team. So we decided
to test our soccer knowledge and our interest for Data Science to pick the best possible lineup which would help us get on the leaderboard. 
We started by getting the up-to-date stats from the Fanatasy Premier League API and study the data to build the most optimal Fantasy League squad with the budget of 
100 million. 

## Hypothesis to test 
Most people use personal bias and favoritism when picking a fantasy team. In other words, people base their decisions on which team they support and on which Premier league player are the "hottest" at the moment. Without even taking a look at individual players as long-term investments. 

## Approch
Our model approch is based on the ROI value associated with each player. 
### ROI value = Total Points of a player / The cost of the player 

## Data Analysis 
    1) We started by making a pandas dataframe by converting the JSON dataframe that we got from the API. 
    2) We plotted a scatter matrix of each column against the other.  
    3) We then started studying this dataframe to slim it down to the columns that we needed. 
    4) By analysing the data we were able to find a coorelation between players and their costs and also what position can get us the maximum points. 
  
## Picking the team 
After looking at different options we settled on a type pf simple constained optimisation model called linear program. 
### Constraints for picking a team
     1) Budget of 100M
     2) Starting line up of 11 players and 4 subs
     3) No more than 3 players from the same team
                          
## Linear Programming 
A linear program allows the efficient exact optimisation of a objective function subject to constraints, where the objective function and the constraints are linear in the decision variables. 

### Example
An example of an integer linear program is as follows
    1) objective function: $F = \sum_{i=0}^{N}x_i V_i$
    2) constraints: $\sum_{i=0}^{N}x_i C_i \le 100$
             $\sum_{i=0}^{N}x_i \le 10$

This describes the following problem: There are $N$ different items in a shop, each with an associated cost $C_i$ and value $V_i$. We indicate whether we buy each item or not with a binary variable $x_i$, so we have 100 variables in total. We want to maximise the total value of the items we buy. However:
  1) we can only spend 100 pounds
  2) we can only buy up to 10 items

## PuLP
PuLP is a linear programming library in Python. It allows you to write down an objective function and constraints in a very intuitive way and instantly solve them.

## Reference 
1) https://ml.christmas/2019/23
2) https://analyticsindiamag.com/how-data-science-can-help-you-win-the-fantasy-premier-league/
3) https://rstudio-pubs-static.s3.amazonaws.com/577042_d4492e2e511848fb97ef839be077e9b8.html
4) https://github.com/joconnor-ml/forecasting-fantasy-football/blob/master/notebooks/Linearly%20Optimising%20FPL%20Teams.ipynb
