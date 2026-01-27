---
layout: page
title: Data Prep & EDA
permalink: /data-prep-eda/
---

## Data Collection

The data used in this project was gathered using the publicly available NBA statistics provided through the [`nba_api`](https://github.com/swar/nba_api), a Python-based interface that allows access to official NBA data endpoints. This API provides structured access to historical and current information on players, teams, games, and season-level statistics. Using an API rather than static datasets allows for reproducibility and flexibility, making it possible to update or extend the analysis as new seasons or data become available. The NBA is particularly well-suited for this type of data-driven exploration due to the consistency of its rules, schedules, and statistical tracking across seasons.

Data was collected by querying specific endpoints within the `nba_api` that return structured JSON responses. These responses were then converted into tabular formats for analysis. The focus of data collection was on season-level and player-level statistics that are commonly referenced in public basketball discussions, such as scoring, efficiency metrics, and games played. The goal was not to capture every available statistic, but rather to gather a representative sample of data that reflects overall performance trends across players and teams. All data used in this project originates from publicly accessible NBA records and does not rely on proprietary or restricted sources.

---

## Data Sources and API Usage

This project relies exclusively on data accessed through the `nba_api`, which serves as a wrapper around official NBA statistics endpoints. The API documentation and source code are available at the following link:

- ***nba_api GitHub Repository:*** https://github.com/swar/nba_api

One core endpoint used for data collection is the **Player Career Statistics** endpoint, which provides season-by-season performance summaries for individual players. This endpoint returns data such as points per game, rebounds, assists, and games played across a player’s career.

**Example API usage (Python):**

```python
from nba_api.stats.endpoints import playercareerstats

player_stats = playercareerstats.PlayerCareerStats(player_id=2544)
player_stats.get_data_frames()[0]

