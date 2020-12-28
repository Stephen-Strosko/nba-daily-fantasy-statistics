# nba-daily-fantasy-statistics

The purpose of this repository is to provide users with a growing collection of daily fantasy NBA statistics.
The scripts in this repository are written in Python, but can be run with zero to no Python experience. Users
will simply need to have Python installed on their computer and the Python packages in the requirements file
installed.

The code in this repository is provided in a Jupyter Notebook, not out of laziness, but for a purpose. Jupyter
Notebooks allow for easy data exploration. Notebooks allow for intermediate and advanced Python users to easily
explore, manipulate, and create custom data, without complicating the script for the beginner.

## NBA Daily Fantasy Data
The first Jupyter Notebook in this repository is titled NBA Daily Fantasy Data and pulls in two disticnt data
sources for users. The first is CBS's basketball statistics: https://www.cbssports.com/fantasy/basketball/stats/
This website does a considerably good job at compiling relevant daily NBA data. The second source is DraftKings
via the library https://github.com/jaebradley/draftkings_client. The result of these two sources is a dataset
that contains statistics for each NBA player that is on a given DraftKings slate - including each player's
salary and average statistics like points per game, minutes per game, rebounds per game, etc.

### Customization
The Jupyter Notebook does need minimal user input to run properly. To begin, users have to choose the length
of data from the CBS website. The choices are season (season_long), the last 7 games (last_7), or the
last 14 games (last_14). The second needed input is the date and time of the DraftKing slate that the user
is interested in. The input for this variable needs to be in UTC time and takes the form YYYY-MM-DD HH:MM
An example would be 2020-12-29 00:30. The Notebook makes it extremely easy to adjust these variables.

### Notes on Requirements
All needed Python requirements are included in the requirements.txt file. Due to the nature of the websites
that this code scrapes, the library Selenium is needed. Selenium requires a Chrome drive to run. Users can 
identify the version of Chrome that they are using by visiting this [site](https://www.whatismybrowser.com/detect/what-version-of-chrome-do-i-have).
Current releases of Google's chromedrivers can be found [here](https://chromedriver.chromium.org/downloads).
Users simply need to download the driver for their current version of Chrome, unzip the file, and add it
to the folder that has the Jupyter Notebook.


### Example data output:
|position|name          |salary|team|fantasy_points_pg|games_played|games_started|minutes_pg|points_pg|field_goal_attempt_pg|field_goal_made_pg|fg% |free_throw_attempt_pg|free_throw_made_pg|ft% |3_point_attempt_pg|3_point_made_pg|3fg%|rebound_pg|assist_pg|steal_pg|turnover_pg|block_pg|
|--------|--------------|------|----|-----------------|------------|-------------|----------|---------|---------------------|------------------|----|---------------------|------------------|----|------------------|---------------|----|----------|---------|--------|-----------|--------|
|PG/SG   |James Harden  |11200 |HOU |79               |1           |1            |43        |44       |22                   |12                |54.5|16                   |14                |87.5|6                 |13             |46.2|4         |17       |1       |4          |0       |
|PG      |Damian Lillard|10300 |POR |41.12            |2           |2            |37.5      |20.5     |20                   |7.5               |37.5|3                    |2.5               |83.3|3                 |10             |30  |4.5       |8        |1       |3          |0.5     |
|PF/C    |Anthony Davis |10100 |LAL |38.88            |2           |2            |30.5      |23       |15.5                 |9                 |58.1|4.5                  |3.5               |77.8|1.5               |3.5            |42.9|7.5       |3.5      |1       |3          |0       |
