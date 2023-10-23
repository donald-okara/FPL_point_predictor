
# Fantasy Premier League Data Analysis

## 1. Teams Filtering
You can find all the relevant APIs and descriptions of each dataframe in this project.

- **Link to APIs**: [Fantasy Premier League APIs](https://www.game-change.co.uk/2023/02/10/a-complete-guide-to-the-fantasy-premier-league-fpl-api/)

### 1.1. Importing Libraries
Before you start with the data analysis, you need to import the necessary libraries. Ensure you've installed these libraries before running the code.

```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
import requests

print("Libraries imported successfully...")
```

### 1.2. Add Fixture Data to the Teams Data

#### 1.2.1. Teams DataFrame (Teams DF)
The following steps explain how to get fixture data for teams:

- Import data from the last season's Fantasy Premier League API.
- Convert the data to a DataFrame.
- Append event IDs to the teams' data for all 38 game weeks.

```python
url = 'https://fantasy.premierleague.com/api/bootstrap-static/'
r = requests.get(url)
json = r.json()

elements_df = pd.DataFrame(json['elements'])
elements_types_df = pd.DataFrame(json['element_types'])
teams_df = pd.DataFrame(json['teams'])

# Function to append event IDs
def append_event_id(teams_df):
    # Create an empty DataFrame to store the expanded data
    expanded_df = pd.DataFrame()

    # Iterate through events from 1 to 38
    for event_id in range(1, 39):
        # Create a temporary DataFrame for the current event
        temp_df = teams_df.copy()

        # Set the 'event_id' column to the current event ID
        temp_df['event_id'] = event_id

        # Append the temporary DataFrame to the expanded DataFrame
        expanded_df = pd.concat([expanded_df, temp_df], ignore_index=True)

    return expanded_df

# Call the function to create an expanded DataFrame with 'event_id'
expanded_teams_df = append_event_id(teams_df)
```

#### 1.2.2. Fixture DataFrame (Fixture DF)
Here, we fetch fixture data for each event:

- Define the base URL for fetching fixture data.
- Iterate through events from 1 to 38.
- Create a temporary DataFrame for the fixture data.
- Append the temporary DataFrame to the expanded fixture DataFrame.

```python
import requests
import pandas as pd

def fetch_fixture_data(event_id):
    # Define the base URL with the event_id
    base_url = f'https://fantasy.premierleague.com/api/fixtures/?event={event_id}'

    # Replace the placeholder '{}' with the actual event_id
    formatted_url = base_url.format(event_id)

    # Send an HTTP GET request to the API endpoint
    response = requests.get(formatted_url)

    # Check if the request was successful (status code 200)
    if response.status_code == 200:
        # Parse the JSON response to get fixture data
        fixture_json = response.json()

        # Create a DataFrame from the fixture data
        fixture_data = pd.DataFrame(fixture_json)

        return fixture_data
    else:
        print(f"Request failed for event {event_id} with status code {response.status_code}")
        return None  # Return None in case of a failed request

# Create an empty DataFrame to store the expanded fixture data
expanded_fixture_df = pd.DataFrame()

# Iterate through events from 1 to 38
for event_id in range(1, 39):
    # Get fixture data for the current event
    fixture_data = fetch_fixture_data(event_id)

    # Create a temporary DataFrame for the fixture data
    temp_df = fixture_data.copy()

    # Set the 'event_id' column to the current event ID
    temp_df['event_id'] = event_id

    # Append the temporary DataFrame to the expanded fixture DataFrame
    expanded_fixture_df = pd.concat([expanded_fixture_df, temp_df], ignore_index=True)

# Renaming columns
expanded_teams_df = expanded_teams_df.rename(columns={'name': 'team_name', 'id': 'team_id', 'short_name': 'team_short_name'})
expanded_fixture_df = expanded_fixture_df.rename(columns={'id': 'fixture_id'})
```

#### 1.2.3. Get Fixture ID
To get the fixture ID for a team in a specific event, you can use the following function:

```python
def get_fixture_id(event_id, team_id):
    for idx, row in expanded_fixture_df.iterrows():
        if event_id == row['event_id']:
            if team_id == row['team_a'] or team_id == row['team_h']:
                return row['fixture_id']
    return None  # Return None if no matching fixture is found

# Assuming you want to calculate and assign fixture IDs for all teams

 in event 1
event_id = 1
expanded_teams_df['fixture_id'] = expanded_teams_df.apply(lambda row: get_fixture_id(event_id, row['team_id']), axis=1)
```

