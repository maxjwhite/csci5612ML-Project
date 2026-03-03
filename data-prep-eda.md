---
layout: page
title: Data Prep & EDA
permalink: /data-prep-eda/
---

## Data Collection
<p style="text-align: justify;">
The data used in this project was gathered using the publicly available NBA statistics provided through the <a href="https://github.com/swar/nba_api" target="_blank">nba_api</a>, a Python-based interface that allows access to official NBA data endpoints. This API provides structured access to historical and current information on players, teams, games, and season-level statistics. The overall goal of the analysis is to determine what defines success in the NBA and what data out there supports that defintion. 
</p>

<p style="text-align: justify;">
Data was collected by querying specific endpoints within the `nba_api` that return structured JSON responses. These responses were then converted into tabular formats for inital exploration through the creation of a collection of visualizations. The focus of data collection was on season-level and player-level statistics that are commonly referenced in public basketball discussions, such as scoring, efficiency metrics, and games played. The goal was not to capture every available statistic, but rather to gather a representative sample of data that reflects overall performance trends across players and teams. All data used in this project originates from publicly accessible NBA records and does not rely on proprietary or restricted sources.
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
    <img src="/csci5612ML-Project/image/before_nba.png" alt="Before" style="width: 400px; height: 300px; object-fit: cover;">
  </div>

  <div style="text-align: center;">
    <p><strong>After</strong></p>
    <img src="/csci5612ML-Project/image/after2_nba.png" alt="After" style="width: 400px; height: 300px; object-fit: cover;">
  </div>

</div>

---
### 🔗 Project Code

The complete implementation for this analysis can be found here in the scripts/eda folder:

[GitHub Repository – NBA Analytics Project](https://github.com/maxjwhite/csci5612ML-NBACode)

---

## Visuals / EDA

<p style="text-align: justify;">
Below are some visuals that were created to get an idea of what the team stats endpoint data looks like along with some intial exploration of feature relationships
</p>

<div style="display: flex; flex-wrap: wrap; gap: 30px; justify-content: center;">

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/wins_nba.png" alt="Wins by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows win counts by each team in the 2024-2025 NBA season. This is an important feature as it is the primary metric for evaluating how a team is performing throughout the regular season.</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/losses_nba.png" alt="Losses by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows loss counts by each team in the 2024-2025 NBA season. Supplementing the 'Wins' chart above, this is just to help futher illustrate the losses feature.</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/winpct_nba.png" alt="Win % by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows win percentage by each team in the 2024-2025 NBA season. A proportion measure that shows the win feature divided by the total games played.</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/points_nba.png" alt="Points per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows points per game by each team in the 2024-2025 NBA season. A measure which averages the points per game which might highlight how effective a team's offense is. </p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/reb_nba.png" alt="Rebounds per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows rebounds per game by each team in the 2024-2025 NBA season. A measure which averages the points allowed per game which might highlight how effective a team's defense is. </p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/assists_nba.png" alt="Assists per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows Assists per game by each team in the 2024-2025 NBA season</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/pointsxwinpct_nba.png" alt="Points vs Win % per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The scatter plot above shows the relationship between points per game and win % by each team in the 2024-2025 NBA season</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/rebxwinpct_nba.png" alt="Rebounds vs Win % per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The scatter plot above shows the relationship between rebounds per game and win % by each team in the 2024-2025 NBA season</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/assistsxwinpct_nba.png" alt="Assists vs Win % per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The scatter plot above shows the relationship between assists per game and win % by each team in the 2024-2025 NBA season</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/pointsxreb_nba.png" alt="Points vs Rebounds per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The scatter plot above shows the relationship between points per game and rebounds per game by each team in the 2024-2025 NBA season</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/pointsxassists_nba.png" alt="Points vs Assists per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The scatter plot above shows the relationship between points per game and assists per game by each team in the 2024-2025 NBA season</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/rebxassists_nba.png" alt="Rebounds vs Assists per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The scatter plot above shows the relationship between rebounds per game and assists per game by each team in the 2024-2025 NBA season</p>
  </div>
  
</div>
