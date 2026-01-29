---
layout: page
title: Data Prep & EDA
permalink: /data-prep-eda/
---

## Data Collection
<p style="text-align: justify;">
The data used in this project was gathered using the publicly available NBA statistics provided through the <a href="https://github.com/swar/nba_api" target="_blank">nba_api</a>, a Python-based interface that allows access to official NBA data endpoints. This API provides structured access to historical and current information on players, teams, games, and season-level statistics. Using an API rather than static datasets allows for reproducibility and flexibility, making it possible to update or extend the analysis as new seasons or data become available. The NBA is particularly well-suited for this type of data-driven exploration due to the consistency of its rules, schedules, and statistical tracking across seasons.
</p>

<p style="text-align: justify;">
Data was collected by querying specific endpoints within the `nba_api` that return structured JSON responses. These responses were then converted into tabular formats for analysis. The focus of data collection was on season-level and player-level statistics that are commonly referenced in public basketball discussions, such as scoring, efficiency metrics, and games played. The goal was not to capture every available statistic, but rather to gather a representative sample of data that reflects overall performance trends across players and teams. All data used in this project originates from publicly accessible NBA records and does not rely on proprietary or restricted sources.
</p>

---

## Data Sources and API Usage

This project relies exclusively on data accessed through the `nba_api`, which serves as a wrapper around official NBA statistics endpoints. The API documentation and source code are available at the following link:

- [***nba_api GitHub Repository:***](https://github.com/swar/nba_api)

One core endpoint used for data collection is the **Player Career Statistics** endpoint, which provides season-by-season performance summaries for individual players. This endpoint returns data such as points per game, rebounds, assists, and games played across a player’s career.

**Example API usage (Python):**

{% highlight python %}
from nba_api.stats.endpoints import playercareerstats

player_stats = playercareerstats.PlayerCareerStats(player_id=2544)
player_stats.get_data_frames()[0]
{% endhighlight %}

## Data Prep and Cleaning
<p style="text-align: justify;">
Most of the data prep and cleaning work was already done before the requests were made. This is thanks to the high quality of the data itself and the efforts of those who work on the 'nba_api' python package which made requesting and reformatting the request objects fairly straightforward. Once the JSON objects were requested, it was just a matter of iterating through the reponse objects and storing them as a dataframe. The data uses full team names in the response object and for the sake of readability, an abbreviated team name feature was created. 
</p>

<div style="display: flex; justify-content: center; gap: 40px; margin: 30px 0;">

  <div style="text-align: center;">
    <p><strong>Before</strong></p>
    <img src="/image/before.png" alt="Before" style="width: 400px; height: auto;">
  </div>

  <div style="text-align: center;">
    <p><strong>After</strong></p>
    <img src="/image/after2.png" alt="After" style="width: 400px; height: auto;">
  </div>

</div>

<p style="text-align: justify;">
The code below shows step by step how the data was requested and reformatted for EDA and visualization. This preliminary exploration focused on endpoints relating to individual player stats and team stats, but there are many other endpoints to explore that would follow a similar pipeline. 
</p>


{% highlight python %}
# !pip install nba_api
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np
from nba_api.stats.static import teams
from nba_api.stats.endpoints import leaguedashteamstats
import warnings
warnings.filterwarnings('ignore')

plt.style.use('seaborn-v0_8')
sns.set_palette("husl")

# Function to get and save team data to CSV
def get_and_save_team_data():
    try:
        team_stats = leaguedashteamstats.LeagueDashTeamStats(
            season='2024-25', 
            season_type_all_star='Regular Season',
            per_mode_detailed='PerGame'
        )
        
        df = team_stats.get_data_frames()[0]
        
        df.to_csv('nba_team_data.csv', index=False)
        print("Data saved to 'nba_team_data.csv'")
        
        return df
        
    except Exception as e:
        print(f"Error fetching data: {e}")
        return None
  {% endhighlight %}
{% highlight python %}
import os
if not os.path.exists('nba_team_data.csv'):
    print("Fetching data from API...")
    team_data = get_and_save_team_data()
    if team_data is None:
        print("Failed to retrieve data. Exiting.")
        exit()
else:
    print("Loading data from CSV...")
    team_data = pd.read_csv('nba_team_data.csv')
    print("Data loaded successfully")

print("\nAvailable columns:")
print(team_data.columns.tolist())
print("\nFirst few rows of data:")
print(team_data.head())

clean_data = []

column_mapping = {
    'TEAM_NAME': 'TEAM_NAME',
    'GP': 'GP',
    'W': 'W',
    'L': 'L',
    'W_PCT': 'W_PCT', 
    'PTS': 'PTS',
    'REB': 'REB',
    'AST': 'AST',
    'FG_PCT': 'FG_PCT',
    'FT_PCT': 'FT_PCT',
    'OPP_PTS': 'OPP_PTS'
}

# Create abbreviation 
team_abbreviations = {
    'Atlanta Hawks': 'ATL',
    'Boston Celtics': 'BOS',
    'Brooklyn Nets': 'BKN',
    'Charlotte Hornets': 'CHO',
    'Chicago Bulls': 'CHI',
    'Cleveland Cavaliers': 'CLE',
    'Dallas Mavericks': 'DAL',
    'Denver Nuggets': 'DEN',
    'Detroit Pistons': 'DET',
    'Golden State Warriors': 'GSW',
    'Houston Rockets': 'HOU',
    'Indiana Pacers': 'IND',
    'Los Angeles Clippers': 'LAC',
    'Los Angeles Lakers': 'LAL',
    'Memphis Grizzlies': 'MEM',
    'Miami Heat': 'MIA',
    'Milwaukee Bucks': 'MIL',
    'Minnesota Timberwolves': 'MIN',
    'New Orleans Pelicans': 'NOP',
    'New York Knicks': 'NYK',
    'Oklahoma City Thunder': 'OKC',
    'Orlando Magic': 'ORL',
    'Philadelphia 76ers': 'PHI',
    'Phoenix Suns': 'PHX',
    'Portland Trail Blazers': 'POR',
    'Sacramento Kings': 'SAC',
    'San Antonio Spurs': 'SAS',
    'Toronto Raptors': 'TOR',
    'Utah Jazz': 'UTA',
    'Washington Wizards': 'WAS'
}

for _, row in team_data.iterrows():
    team_name = row.get('TEAM_NAME', 'Unknown')
    abbrev = team_abbreviations.get(team_name, team_name)
    clean_row = {
        'TEAM_NAME': team_name,
        'TEAM_ABBREV': abbrev,
        'GP': row.get('GP', 0),
        'W': row.get('W', 0),
        'L': row.get('L', 0),
        'W_PCT': row.get('W_PCT', 0),  
        'PTS': row.get('PTS', 0),
        'REB': row.get('REB', 0),
        'AST': row.get('AST', 0),
        'FG_PCT': row.get('FG_PCT', 0),
        'FT_PCT': row.get('FT_PCT', 0),
        'OPP_PTS': row.get('OPP_PTS', 0)
    }
    clean_data.append(clean_row)

clean_df = pd.DataFrame(clean_data)

clean_df['W_PCT'] = pd.to_numeric(clean_df['W_PCT'], errors='coerce')
{% endhighlight %}



