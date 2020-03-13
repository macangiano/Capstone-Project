# Predicting World Cup Group Stage Outcomes
    By Matteo Cangiano
## Table of Contents
  - [Problem Statement](#Problem-Statement)
  - [Executive Summary](#Executive-Summary)
  - [Data Collection](#Data-Collection)
  - [Conclusions and Recommendations](#Conclusions-and-Recommendations)

## Problem Statement
The Italian Football Federation has asked to create a model that would predict whether or not Italy will pass the group stage of the 2014 World Cup. Progressing to the later stages of the World Cup brings extra funds as well as more marketing for the team, increasing their chance of future successes. With these funds’ teams are able to invest in their domestic leagues and youth development. For this project I will be using past World Cup data on matches as well as player ratings from FIFA 14. Using a classification model with a metric of accuracy, I will predict the outcome of the group stage for Group D (the group Italy is in).


## Executive Summary

This project is being developed for the Italian Football Federation (FIGC) an organization that oversees soccer in Italy as well as the international team for european and world competitions such as the World Cup. The winner of the World Cup receives $38 million as prize money to then cover their costs and invest in the future of the sport within their country. Just by passing the group stages a team will receive $12 million, which can go a long way in upgrading technology and developing youth. We developed a machine learning-based tool that can predict the outcome of the group stages, allowing the FIGC to plan for future investments.

The problem statement asked to create a model that would predict whether or not Italy will pass the group stage of the 2014 World Cup. Due to the limited time we decided to leave out some data that will later be mentioned in the ‘Recommendations’ section to improve model performance.

Instead we found two datasets, one on the FIFA ratings for the year 2014 and the other on historical World Cup matches dating back to 1930. Combining the two datasets allowed us to better predict the outcomes by analyzing past records and form against certain teams as well as the current team status. Preliminary EDA showed that the ratings from the FIFA dataset could be trusted as they corresponded with the national team rankings and public opinion. It also showed us that based on the difference between the mean statistics of two teams, the model should be able to distinguish which team would win the head-to-head. 

Once the datasets were ready we began fitting different classification models to predict the probability that one team would win over the other. Subsequently, we created functions that would take into the consideration the attributes of both teams and predict the winner via simulations. Each game was simulated 1000 times to ensure accurate scores. Our model is able to correctly predict the outcome of any given match with 61% accuracy. However, it must be noted that “the beautiful game” is highly unpredictable as we can see from the results of the actual outcomes of the group stages, leaving many in shock to see smaller teams such as Costa Rica come out on top. This model can give us an idea of how a game should turn out on paper, but anything can happen once the players are on the field. 

## Data Collection

For the purpose of this project we decided to use only the teams and players that were involved in the 2014 world cup, both to improve accuracy of the model eliminating the possibility of outliers as well as the computational efficiency of the model and simulations.

The datasets used:
  - [FIFA 14 Player Ratings](#./datasets/players_18.csv)
  - [World Cup Matches](#./datasets/WorldCupMatches.csv)


## Conclusion and Recommendations

The model is able to predict with 61% accuracy which team will win. The model which worked best according to the accuracy score was the Voting Classifier. The simulating of the individual games sometimes seems more accurate using different classifier models on the simulation functions. However, the overall outcome of the group is best predicted by the Voting Classifier which uses a tuned Extra Trees model. There are many considerations to make when trying to predict the future as there is always a level of uncertainty present. This particular group in the 2014 World Cup was a prime example of this as the world watched Costa Rica put on a performance of a life time causing huge upsets and ultimately winning the group. The best we can do is use this data to identify what makes a winning team by looking at the coefficients of the model. This information could be of great use to international teams looking for areas in need of improvement. Ultimately my goal was to predict whether or not Italy would pass the group stages. According to my model Italy should have passed easily winning two out of the three games. However, this proved to be Costa Rica's year and the Italian nationals ended up going home.

The model can be improved in the future by giving it more data on each team. This became evident when we found leakage due to the 'score' column in our dataset. The model was able to take this information and correctly predict the outcome every time. What can be done to include the goal scoring factor into the model would be to calculate the probability of a given team to score against another. This way our features would be able to take into consideration the goal scoring ability of each squad without having it directly inform the model on who the winner is. Furthermore, for the feasibility of this project we only ran my model on games that included teams from the 2014 World Cup. A next step would be to include all matches as the model would have more data to work with. Since the model examines the relationships between the team’s average statistics rather than the team names, it would not have an impact on the outcome.

