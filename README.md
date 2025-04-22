# League of Legends the affect of Team Composition on Win Rate
by Marc Rosenberg (cramr@umich.edu)

---
##Introduction
League of Legends is a massively popular multiplayer online battle arena game produced by riot games and played by more than 150 million players worldwide making it the most popular multiplayer online battle arena of all time. In league of legends two teams of five players compete to destroy each other's nexus each of the players chooses a champion from among League of Legends roster of 170 champions. In casual games and even more so in professional games the team composition or the set of 5 champions that a team decides to play is often a deciding factor in who wins or loses a match. The aim of this project is to answer the question: does team composition affect the likelihood of winning a game of winning a game of league of legends?

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

---
## Data Cleaning and Exploratory Analysis
### Data Cleaning
#### Column and Row Selection
> First we select the relevant columns in the main data frame I selected pick1 pick2 pick3 pick4 pick5 an result in the second data frame no column selection is needed since both columns are important. In the main data frame we select only the summary rows which include all the picks as well as the result.
#### Merging Tables
> I merged the data tables in two different ways, the first way was simply replacing each champion name in pick1 through pick5 with the champion class this is used later in order to compare total team compositions. The second way I merged my datasets was by first counting the number of wins and losses each champion had individually before merging on champion names then grouping by champion class and adding up the wins and losses per class.
#### Win Rate and Data Filtering
> Since the main question of the project relates team composition to win rate I added a win rate calculation to both data frames the first table has win rates by class while the second has win rate by team composition. The second graph that has win rate by team composition has two additional steps as well the first is agregating the team compositions any team composition with the same number of each class is considered the same and added together. The other additional step is filtering by the count of number of team compositions, since some compositions are much more popular than others it is necessary to only consider the compositions where there are enough games which for this project I will consider to be 50.

| compisition                             | count  | wins | win_rate |
|:----------------------------------------|--------|------|---------:|
|(Fighter, Fighter, Mage, Mage, Marksman) | 70	   |41	  | 0.59     |

| Class	| Wins | Losses | Win Percentage |
|:----------------------------------------|--------|------|---------:|
| Marksman | 10959 | 10875 | 50.19 |

### Univerate Analysis

 <iframe
 src="win_per_class.html"
 width="800"
 height="600"
 frameborder="0"
 ></iframe>

The above plot shows the win rate by class the graph is zoomed in to a 3% range around 50% and although there appears to be a large difference between classes it is mostly due to the zoom. The difference between classes is actually relativley small suggesting a relative parity in winrates between classes.

### Bivariate Analysis

 <iframe
 src="win_vs_role.html"
 width="800"
 height="600"
 frameborder="0"
 ></iframe>

The above plot demonstrates the relationship between the number of unique classes in a team composition against their win rate. Although the median and max arent very different between the three different types of team composition the minimum and q1 on the teams with 5 different classes is much higher suggesting that a more diverse team is often better.

### Interesting Aggregates
The main table that I aggregated was previously mentioned and that is the aggregate of the wins and losses per team composition which is the following table.




