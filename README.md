# League of Legends the affect of Team Composition on Win Rate
by Marc Rosenberg (cramr@umich.edu)

---
##Introduction
League of Legends is a massively popular multiplayer online battle arena game produced by riot games and played by more than 150 million players worldwide making it the most popular multiplayer online battle arena of all time. In league of legends two teams of five players compete to destroy each other's nexus each of the players chooses a champion from among League of Legends roster of 170 champions. In casual games and even more so in professional games the team composition or the set of 5 champions that a team decides to play is often a deciding factor in who wins or loses a match. The aim of this project is to answer the question: does team composition affect the likelihood of winning a game of winning a game of league of legends.

To begin with we need to slightly redefine the meaning of team composition. Since there are 170 champions currently within league of legends the number of possible team compositions we could have would be 170\*169\*168\*167\*166 or 133,804,114,080 which is far too many. So instead I used official league of legends data to match each champion to their corresponding class of which there are 7 (shown below) meaning that the maximum number of team compositions would be 7^5 or 16,807 which although still alot is far more manageable.

| Class       |  
|:-----------:|
| Marksman    |
| Fighter     |
| Slayer      |
| Tank        |
| Mage        |
| Controller  |
| Specialist  |

The main data set has a total of 115152 rows with every 12 rows representing a single game between two teams each team has 6 rows of data one for each player and one for an overall team summary. In addition I used a second supplementary data set that I created using the league of legends wiki this data set has a list of champions and their corresponding classes.

In the main data set I used the following columns:

| Column      | Contents           |
|:------------|-------------------:|
| pick1       | Champion name      |
| pick2       | Champion name      |
| pick3       | Champion name      |
| pick4       | Champion name      |
| pick5       | Champion name      |
| result      | 1 if win 0 if loss |

The second data set has the following columns:

| Column      | Contents           |
|:------------|-------------------:|
| Champion    | Champion name      |
| Class       | Class name         |


