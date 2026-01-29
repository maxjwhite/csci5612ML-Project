---
layout: page
title: Introduction
permalink: /
---
![Wide-angle view of a professional basketball game](https://images.unsplash.com/photo-1546519638-68e109498ffc?auto=format&fit=crop&w=1600&q=80)
<p style="text-align: justify;">
The National Basketball Association (NBA) is one of the most popular and closely followed professional sports leagues in the world, attracting fans, analysts, media organizations, and team decision-makers alike. Beyond entertainment, the NBA has become a space where data plays an increasingly important role in shaping how the game is understood and discussed. Every season, thousands of games generate detailed records of player performance, team outcomes, and league-wide trends. These data help frame conversations about success, improvement, and competitive balance across the league. For fans, data-driven insights provide deeper context for what happens on the court. For teams and players, performance statistics can influence evaluations, contracts, and career trajectories. As analytics becomes more visible in sports coverage, it is important to understand what stories the data can meaningfully tell. Basketball’s structured gameplay and consistent rules make it especially well-suited for systematic analysis. Examining NBA data allows us to explore broader questions about performance and consistency in a familiar setting. This project focuses on analyzing NBA data to better understand patterns that emerge across players, teams, and seasons.
</p>

<p style="text-align: justify;">
The data used in this project is gathered from publicly available NBA statistics accessed through the <a href="https://github.com/swar/nba_api" target="_blank">nba_api</a>, a community-supported interface that provides structured access to official league data. This source aggregates historical and current information that is commonly referenced in media coverage and public discussions of the NBA. Using an open and reproducible data source ensures transparency in how insights are derived and allows findings to be easily revisited or extended. Over the past decade, analysts and researchers have used similar data to study topics such as scoring trends, efficiency, and the impact of individual players. While professional teams often rely on proprietary tools, public NBA data offers a valuable opportunity for independent exploration. However, raw statistics do not always tell a complete story without thoughtful interpretation. Context, comparison, and variation across seasons all influence how numbers should be understood. By examining NBA data from multiple perspectives, this project aims to clarify how performance patterns develop over time. The goal is not to predict outcomes, but to better interpret what the available data reveals. Ultimately, this analysis seeks to make NBA data more accessible and informative for a general audience.
</p>

---

## Questions of Interest
- How have scoring patterns in the NBA changed over time across different teams and seasons?
- Are certain teams consistently more efficient than others, and how stable is that efficiency year to year?
- What statistical differences tend to separate winning teams from losing teams?
- How much variation exists in player performance within the same team?
- Do teams with a small number of high-performing players differ from more balanced teams in outcomes?
- Are there identifiable trends in team play styles across the league?
- How does player workload relate to overall team success?
- Are some teams more consistent than others across a season?
- Do statistical indicators differ significantly between playoff and non-playoff teams?
- What patterns emerge when comparing teams across conferences or divisions?

---

## Visuals / EDA

<p style="text-align: justify;">
Below are some visuals that were created to get an idea of what the team stats endpoint data looks like along with some intial exploration of feature relationships
</p>

<div style="display: flex; flex-wrap: wrap; gap: 30px; justify-content: center;">

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/wins_nba.png" alt="Wins by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows win counts by each team in the 2024-2025 NBA season.</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/losses_nba.png" alt="Losses by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows loss counts by each team in the 2024-2025 NBA season.</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/winpct_nba.png" alt="Win % by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows win percentage by each team in the 2024-2025 NBA season</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/points_nba.png" alt="Points per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows points per game by each team in the 2024-2025 NBA season</p>
  </div>

  <div style="text-align: center;">
    <img src="{{ site.baseurl }}/image/reb_nba.png" alt="Rebounds per game by NBA Team" style="width: 500px; height: auto; border-radius: 6px;">
    <p style="font-size: 0.9em; color: #555;">The graph above shows rebounds per game by each team in the 2024-2025 NBA season</p>
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
