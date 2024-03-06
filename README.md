Astana IT University

Advanced Programming | Python

Project Title: Football Match Predictor

Student Contributors: Ilyarzhan Assimov, Zhanet Bolatova, Aizhan Qundyzbek

Group: IT-2201

Project Supervisor: Yeleu Sultanmurat

Date: March 2024

Github https://github.com/ilyarjan1/football-score-prediction
YouTube 
Contents

Introduction

Statement of the Problem

Review of Literature and References

Ongoing Work

Data Sources and Methodology

Description of Data

Overview of the ML Model

Findings

Discussion and Analysis

Review and Critical Evaluation

Challenges and Future Directions

Introduction

For an overview, watch our YouTube video at [YouTube Video Link] and check our GitHub repository at [GitHub Link].

Problem
Football, the most beloved sport globally, lends itself to various applications such as betting, fan engagement, and data analysis. Our project aims to utilize neural networks to predict football match outcomes based on teams' historical performances.

Literature Review and References
We sourced all team statistics from https://understat.com/ via bs4.BeautifulSoup, a resource that offers detailed statistics for games in the top 5 European Leagues (EPL, Serie A, Bundesliga, La Liga, Ligue 1). For a GitHub reference, see https://github.com/krishnakartik1/LSTM-footballMatchWinner.

Current Work
Our model utilizes 60% of the data for training and 40% for validation. The training accuracy is around 51%, with the validation accuracy close to 49%. As football outcomes are influenced by many factors beyond mere statistics, a 50% prediction accuracy is a significant achievement.

Data and Methods
Data Description

The data encapsulates average performance metrics from teams' last 5, 10, 15, 25, and 38 games. The most indicative stats are from the last 5 and 10 games, reflecting the teams' current condition. Each team's stats are presented in a 50-item array. The dataset spans matches from August 2014 to the present.

Details:

'h/a': Indicates whether the team is hosting or visiting.
'TEAMS': Team names (not included in the statistical array).
'CHANCES': The ratio of dangerous to total attacks.
'GOALS': Total goals scored.
'RESULT': Match result (0 – draw, 1 – won, 2 – lost) (not in the statistical array).
'POINTS': Points earned (0 – lost, 1 – draw, 3 – won).
'xG': Expected goals.
'SHOTS': Total shots taken.
'SHOTS ON TARGET': Shots on target, excluding crossbars or deflections.
'DEEP': Number of successful passes in the opponent's goal area.
'PPDA': Passes allowed per defensive action in the opponent's half.
'xPTS': Expected points, based on expected goals and other metrics.
Model input: [first_team_stat, second_team_stat]
The dataset comprises 15,444 matches involving 1 club.

ML Model Description
Our neural network model is structured to forecast football match results. It features multiple dense layers, each with ReLU activation functions and dropout regularization to counter overfitting. The first two layers contain 128 neurons each, followed by two layers with 64 neurons. The final layer has 3 neurons with a softmax activation function, producing probabilities for each possible match outcome. The model employs the Adam optimizer and sparse_categorical_crossentropy loss function, suitable for multi-class classification. It includes an EarlyStopping callback to halt training if validation loss doesn't improve after 5 epochs.

Results
Our model predicts the likelihood of each team winning or a draw. For instance, in a match between Manchester City and RasenBallsport Leipzig, Manchester City has a 62.63% winning chance, Leipzig 15.12%, and a 22.25% probability for a draw.

Discussion
Critical Review

While the prediction favors Manchester City, such forecasts depend on numerous factors beyond our model's scope. Factors like player conditions, team strategies, and unforeseen circumstances can significantly sway match outcomes.

Limitations and Future Work
Our project currently relies solely on statistical data, excluding advanced metrics and subjective elements like player morale and coaching strategies. The model's accuracy could improve with more data and advanced architectures. Currently, it only covers the top 5 European leagues and might miss out on other global matches. Future expansions may include more comprehensive data and other leagues.






