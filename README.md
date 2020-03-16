# NCAA-Fantasy-Grade-Competition

I've been working on this NCAA Wrestling project for quite a while now. I will outline the overall steps I have taken to finally finish the project:

1. Scrape 2019 tournament data from Bracket Sheet pdf file.
2. Create scoring scripts to obtain scoring data for each 2019 athlete.
3. Build, train, optimize the neural network for predicting scores base on the 2019 data (sent by WrestleStat).
4. Scrape 2020 season data from WrestleStat website.
5. Scrape 2020 FantasyGrade ranks and caps to then merge with WrestleStat data.
6. Run 2020 data through the neural network to get predicted scores.
7. Create script that finds the overall predicted highest scoring fantasy team, while staying under the cap of 1000 required by FantasyGrade. (FantasyGrade_Scrape.ipynb)

Overall, results seem very good. I output the top 4 highest scoring teams:

Top 4 Teams:

('spencer lee', 'taylor lamont', 'nick lee', 'austin oxconnor', 'tyler eischens', 'vincenzo joseph', 'jordan kutler', 'alan clothier', 'shakur rasheed', 'gable steveson')
Projected Score: 154.75938165187836

('nicholas piccininni', 'taylor lamont', 'nick lee', 'matthew kolodzik', 'kaleb young', 'vincenzo joseph', 'michael kemerer', 'alan clothier', 'shakur rasheed', 'gable steveson')
Projected Score: 154.76101768016815

('nicholas piccininni', 'taylor lamont', 'nick lee', 'matthew kolodzik', 'tyler eischens', 'evan wick', 'michael kemerer', 'aaron brooks', 'shakur rasheed', 'gable steveson')
Projected Score: 155.111891746521

('nicholas piccininni', 'taylor lamont', 'nick lee', 'austin oxconnor', 'tyler eischens', 'vincenzo joseph', 'mark hall', 'alan clothier', 'shakur rasheed', 'gable steveson')
Projected Score: 155.87799203395844

A few things about these teams that lead me to believe the model has done relatively well:
1. It picked the same type of team structure that typically wins: allow yourself to waste cap on multiple high scorers by picking a couple low scorers (alan clothier and tyler eischens). This team structure is great due to the exponential distribution of scores. Very high scorers are hard to come by.
2. It picked Taylor Lamont every time. This was obvious. Some might say he is a national title contender, but only a 10 cap due to a very odd season. Most wrestling fans would say this is a no brainer; it's cool that the model picked up on this.
3. The winning score the last 3 years for this competition were 155, 157, and 155. This leads me to believe that these teams (if the predictions are accurate) are in the ballpark of the best scoring teams.

Sadly, I will not be able to play the competition this year as the tournament was cancelled due to COVID-19. I will have to wait until 2021 to see how it performs. Either way, this was a very fun project and I learned a ton completing it.

note: The Plotly displays are not visible in the GitHub display of ipynb files. They are scatter plots of all wrestlers cap by predicted score with mouse over feature to see names of all wrestlers. The script will have to be compiled to see these outputs.
