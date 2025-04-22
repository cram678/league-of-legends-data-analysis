# League of Legends the affect of Team Composition on Win Rate
by Marc Rosenberg (cramr@umich.edu)

---
#Introduction
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
