### Player History

Here is a description of every column in the "player history" table in the FPL API, in Markdown format with each column bulleted:

- **id:** The unique identifier of the player.
- **round:** The round number of the gameweek.
- **season_name:** The name of the season.
- **team_code:** The unique identifier of the player's team.
- **opponent_code:** The unique identifier of the player's opponent's team.
- **total_points:** The player's total number of points for the gameweek.
- **minutes:** The number of minutes that the player played in the gameweek.
- **goals_scored:** The number of goals that the player scored in the gameweek.
- **assists:** The number of assists that the player provided in the gameweek.
- **clean_sheets:** The number of clean sheets that the player kept in the gameweek.
- **goals_conceded:** The number of goals that the player conceded in the gameweek.
- **own_goals:** The number of own goals that the player scored in the gameweek.
- **penalties_saved:** The number of penalties that the player saved in the gameweek.
- **yellow_cards:** The number of yellow cards that the player received in the gameweek.
- **red_cards:** The number of red cards that the player received in the gameweek.
- **saves:** The number of saves that the player made in the gameweek.
- **bonus:** The number of bonus points that the player received in the gameweek.
- **bps:** The player's bonus points system score for the gameweek.
- **influence:** The player's influence score for the gameweek.
- **creativity:** The player's creativity score for the gameweek.
- **threat:** The player's threat score for the gameweek.
- **ict_index:** The player's ict index for the gameweek.
- **ea_index:** The player's ea index for the gameweek.
- **element_type:** The player's position, which can be one of the following:
    - **1:** Goalkeeper
    - **2:** Defender
    - **3:** Midfielder
    - **4:** Forward

You can use this information to track the performance of players over time and to identify players who are in good form.

### Player History Past

Here is a description of every column in the "player history" table in the FPL API, in Markdown format with each column bulleted:

- **id:** The unique identifier of the player.
- **round:** The round number of the gameweek.
- **season_name:** The name of the season.
- **team_code:** The unique identifier of the player's team.
- **opponent_code:** The unique identifier of the player's opponent's team.
- **total_points:** The player's total number of points for the gameweek.
- **minutes:** The number of minutes that the player played in the gameweek.
- **goals_scored:** The number of goals that the player scored in the gameweek.
- **assists:** The number of assists that the player provided in the gameweek.
- **clean_sheets:** The number of clean sheets that the player kept in the gameweek.
- **goals_conceded:** The number of goals that the player conceded in the gameweek.
- **own_goals:** The number of own goals that the player scored in the gameweek.
- **penalties_saved:** The number of penalties that the player saved in the gameweek.
- **yellow_cards:** The number of yellow cards that the player received in the gameweek.
- **red_cards:** The number of red cards that the player received in the gameweek.
- **saves:** The number of saves that the player made in the gameweek.
- **bonus:** The number of bonus points that the player received in the gameweek.
- **bps:** The player's bonus points system score for the gameweek.
- **influence:** The player's influence score for the gameweek.
- **creativity:** The player's creativity score for the gameweek.
- **threat:** The player's threat score for the gameweek.
- **ict_index:** The player's ict index for the gameweek.
- **ea_index:** The player's ea index for the gameweek.
- **element_type:** The player's position, which can be one of the following:
    - **1:** Goalkeeper
    - **2:** Defender
    - **3:** Midfielder
    - **4:** Forward

You can use this information to track the performance of players over time and to identify players who are in good form.

### Player Fixtures

Here is a description of every column in the "player fixtures" table in the FPL API in markdown format:

- **id:** The unique identifier of the fixture.
- **kickoff_time:** The kickoff time of the fixture, in UTC.
- **event:** The gameweek number of the fixture.
- **finished:** Whether the fixture has finished.
- **provisional_start_time:** The provisional start time of the fixture, in UTC.
- **finished_provisional:** Whether the fixture has finished provisionally.
- **home_team:** The home team.
- **away_team:** The away team.
- **stats:** A list of player statistics for the fixture.
- **team_h_difficulty:** The difficulty of the home team, based on their recent form.
- **team_a_difficulty:** The difficulty of the away team, based on their recent form.
- **home_team_strength:** The strength of the home team, based on their recent form.
- **away_team_strength:** The strength of the away team, based on their recent form.
- **home_team_form:** The form of the home team, based on their recent results.
- **away_team_form:** The form of the away team, based on their recent results.
- **home_team_attack:** The attack of the home team, based on their recent form.
- **away_team_attack:** The attack of the away team, based on their recent form.
- **home_team_defence:** The defence of the home team, based on their recent form.
- **away_team_defence:** The defence of the away team, based on their recent form.
- **home_team_attack_strength:** The attack strength of the home team, based on their recent form.
- **away_team_attack_strength:** The attack strength of the away team, based on their recent form.
- **home_team_defence_strength:** The defence strength of the home team, based on their recent form.
- **away_team_defence_strength:** The defence strength of the away team, based on their recent form.
- **home_team_goals_scored:** The number of goals scored by the home team in their recent matches.
- **away_team_goals_scored:** The number of goals scored by the away team in their recent matches.
- **home_team_goals_conceded:** The number of goals conceded by the home team in their recent matches.
- **away_team_goals_conceded:** The number of goals conceded by the away team in their recent matches.
- **home_team_clean_sheets:** The number of clean sheets kept by the home team in their recent matches.
- **away_team_clean_sheets:** The number of clean sheets kept by the away team in their recent matches.
- **home_team_form_attack:** The form of the home team's attack, based on their recent results.
- **away_team_form_attack:** The form of the away team's attack, based on their recent results.
- **home_team_form_defence:** The form of the home team's defence, based on their recent results.
- **away_team_form_defence:** The form of the away team's defence, based on their recent results.

You can use this information to analyze the upcoming fixtures and to make informed decisions about your FPL team. For example, you could use the `team_h_difficulty` column to identify teams that are likely to be difficult for your players to score against. Or, you could use the `home_team_goals_scored` column to identify teams that are likely to score a lot of goals in their upcoming fixtures.

> The column name might not match the one in the data frames as this is a summarization compiled after scouring the web. 
> 
> Cheers !!