# FPL_point_predictor
### 1. Teams Filtering
This section of the code focuses on filtering and processing data related to Fantasy Premier League (FPL) teams. It does the following:

**a) Importing Libraries:** The code starts by importing essential libraries for data manipulation and visualization, including Pandas, NumPy, Seaborn, Matplotlib, and Requests.

**b) Add Fixture Data to Teams Data:**
   - The code first fetches data about FPL teams from the given API URL.
   - It then appends the 'event_id' to each row in the teams DataFrame, creating an expanded DataFrame with event-specific data.
   
**c) Fetch Fixture Data:**
   - This function, `fetch_fixture_data(event_id)`, is defined to fetch fixture data for a specific event (gameweek) from the FPL API.
   - It sends an HTTP GET request to the API, retrieves fixture data, and converts it into a DataFrame.

**d) Get Fixture ID:**
   - The function `get_fixture_id(event_id, team_id)` retrieves the fixture ID for a given event and team. It iterates through the fixture data to find the matching fixture ID.

**e) Get Fixture Difficulty:**
   - The function `get_fixture_difficulty(team_id, fixture_id)` calculates the fixture difficulty for a given team and fixture. It checks if the team is playing at home or away and assigns the corresponding fixture difficulty.

**f) Team and Opponent Score:**
   - Two functions, `get_opponent_team(team_id, fixture_id)` and `get_opponent_score(team_id, fixture_id)`, determine the opponent team and opponent's score for a given team and fixture.
   - They also check if the team is playing at home or away to make the assignment correctly.

**g) Team Score:**
   - The function `get_team_score(team_id, fixture_id)` calculates and assigns the team's score for a given team and fixture.
   - It considers whether the team is playing at home or away.

**h) Game Played:**
   - The function `get_finished_status(team_id, fixture_id)` determines whether a game has been played (finished) for a given team and fixture.

**i) If Fixture Is Home:**
   - The function `get_home_status(team_id, fixture_id)` checks if a fixture is a home game for a given team.

**j) If Deadline Passed:**
   - The function `get_kickoff_time(team_id, fixture_id)` retrieves the kickoff time for a given team and fixture.

**k) Gameweek Deadline Variable:**
   - This section calculates the gameweek deadline by filtering the DataFrame to get events where the game hasn't started ('started' is False) and sorting them by 'kickoff_time'. It then sets the gameweek deadline as an hour before the kickoff time of the first event.

**l) Feature Engineering for Team Data:**
   - This section of the code creates several features for team data, such as games played, total goals, goals per game, goals conceded, win, draw, loss, total wins, win percentage, game results, form, numerical form, strength, and more.

**m) Home Stats:**
   - Similar to feature engineering for overall team data, this section focuses on creating features related to home game statistics.

**n) Away Stats:**
   - Similar to the previous sections, this part creates features related to away game statistics.

**o) Defense Strength Stats:**
   - It calculates defensive strength statistics for teams, including overall, home, and away.

**p) Attack Strength Stats:**
   - Similar to defense strength, this section calculates attack strength statistics for teams.

**q) Preprocessing:**
   - In this part, data preprocessing is performed, including normalizing selected columns using the Min-Max scaler.

**r) Filtered Teams:**
   - Finally, the code selects specific columns from the DataFrame to create a filtered version of the teams' data.

### 2. Manager Data
This section focuses on gathering data related to an FPL manager's team for a specific gameweek. It does the following:

**a) Importing Libraries:** Similar to the previous sections, essential libraries are imported.

**b) Retrieving Manager's Team Data:**
   - The code defines a function to retrieve the FPL manager's team data for a specific gameweek. It sends an API request to the FPL API, collects data about the manager's team, including player selections, chips, and entry history, and formats it into a DataFrame.

**c) FPL Team Data:**
   - It selects specific columns related to the manager's FPL team, including active chips, player selections, and other relevant information.

### 3. Model Training
This section focuses on training a machine learning model for player data prediction. It does the following:

**a) Importing Libraries:** Similar to previous sections

, the code starts by importing necessary libraries.

**b) Define Function to Format Player Data URL:**
   - A function is defined to format the URL for fetching player data from the FPL API.

**c) Fetch Player Data:**
   - This part of the code fetches player data for the current season from the FPL API, including data about players, their positions, teams, and other relevant information.

**d) Data Cleaning:**
   - It cleans the player data, removes unnecessary columns, and formats the data into a DataFrame for model training.

**e) Train Model:**
   - A function, `train_model`, is defined for training a machine learning model using scikit-learn and TensorFlow. The model consists of several steps, including feature selection, standard scaling, and building a neural network for prediction.

This code represents a comprehensive data analysis and modeling pipeline for Fantasy Premier League data, covering data retrieval, preprocessing, feature engineering, and machine learning model training for predicting player performance metrics.
