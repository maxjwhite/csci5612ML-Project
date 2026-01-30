---
layout: page
title: Introduction
permalink: /
---
![Wide-angle view of a professional basketball game](https://images.unsplash.com/photo-1546519638-68e109498ffc?auto=format&fit=crop&w=1600&q=80)
<p style="text-align: justify;">
The National Basketball Association (NBA) is one of the most popular and closely followed professional sports leagues in the world, attracting fans, analysts, media organizations, and team decision-makers alike. Beyond entertainment, the NBA has become a space where data plays an increasingly important role in shaping how the game is understood and discussed. Every season, thousands of games generate loads of data on player performance, team outcomes, and league-wide trends. This data helps frame conversations about success, improvement, and competitive balance across the league. For fans, data-driven insights provide deeper context for what happens on the court. For teams and players, performance statistics can influence evaluations, contracts, and career trajectories. As analytics becomes more visible in sports coverage, it is important to understand what stories the data can meaningfully tell. Basketball’s structured gameplay and consistent rules make it especially well-suited for systematic analysis. Examining NBA data allows us to explore broader questions about performance and consistency in a familiar setting. This project focuses on analyzing NBA data to better understand patterns that emerge across players, teams, and seasons.
</p>

<p style="text-align: justify;">
The data used in this project is gathered from publicly available NBA statistics accessed through the <a href="https://github.com/swar/nba_api" target="_blank">nba_api</a>, a community-supported repository that provides structured access to official league data. This source aggregates historical and current information that is commonly referenced in media coverage and public discussions of the NBA. Over the past decade, analysts and researchers have used similar data to study topics such as scoring trends, efficiency, and the impact of individual players. While professional teams often rely on proprietary tools, public NBA data offers a valuable opportunity for independent exploration. However, raw statistics do not always tell a complete story without interpretation. Context, comparison, and variation across seasons all influence how the data should be understood. By examining NBA data from multiple perspectives, this project aims to clarify how performance patterns develop over time. The goal is not to predict outcomes, but to better interpret what the available data reveals. Ultimately, this project seeks to shed a bit more light on what makes a Championship team in the NBA. 
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

<p style="text-align: justify;">
Code to replicate figures above. See Data Prep and EDA tab for code to request and prepare data for figures. 
</p>

{% highlight python %}
plt.figure(figsize=(10, 6))
plt.bar(range(len(clean_df)), clean_df['W'], color='skyblue')
plt.title('Wins by Team')
plt.xticks(range(len(clean_df)), clean_df['TEAM_ABBREV'], rotation=45, ha='right')
plt.ylabel('Wins')
plt.tight_layout()
plt.show()

# 2. Team Performance by Losses
plt.figure(figsize=(10, 6))
plt.bar(range(len(clean_df)), clean_df['L'], color='lightcoral')
plt.title('Losses by Team')
plt.xticks(range(len(clean_df)), clean_df['TEAM_ABBREV'], rotation=45, ha='right')
plt.ylabel('Losses')
plt.tight_layout()
plt.show()

# 3. Team Performance by Win Percentage
plt.figure(figsize=(10, 6))
plt.bar(range(len(clean_df)), clean_df['W_PCT'], color='lightgreen')
plt.title('Win Percentage by Team')
plt.xticks(range(len(clean_df)), clean_df['TEAM_ABBREV'], rotation=45, ha='right')
plt.ylabel('Win Percentage')
plt.ylim(0, 1)
plt.tight_layout()
plt.show()

# 4. Points Scored by Team
plt.figure(figsize=(10, 6))
plt.bar(range(len(clean_df)), clean_df['PTS'], color='orange')
plt.title('Points Scored by Team')
plt.xticks(range(len(clean_df)), clean_df['TEAM_ABBREV'], rotation=45, ha='right')
plt.ylabel('Points')
plt.tight_layout()
plt.show()

# 5. Rebounds by Team
plt.figure(figsize=(10, 6))
plt.bar(range(len(clean_df)), clean_df['REB'], color='purple')
plt.title('Rebounds by Team')
plt.xticks(range(len(clean_df)), clean_df['TEAM_ABBREV'], rotation=45, ha='right')
plt.ylabel('Rebounds')
plt.tight_layout()
plt.show()

# 6. Assists by Team
plt.figure(figsize=(10, 6))
plt.bar(range(len(clean_df)), clean_df['AST'], color='red')
plt.title('Assists by Team')
plt.xticks(range(len(clean_df)), clean_df['TEAM_ABBREV'], rotation=45, ha='right')
plt.ylabel('Assists')
plt.tight_layout()
plt.show()

# 7. Points vs Win Percentage
plt.figure(figsize=(10, 6))
plt.scatter(clean_df['PTS'], clean_df['W_PCT'], alpha=0.7, color='blue')
plt.title('Points vs Win Percentage')
plt.xlabel('Points Scored')
plt.ylabel('Win Percentage')
for i, abbrev in enumerate(clean_df['TEAM_ABBREV']):
    plt.annotate(abbrev, (clean_df['PTS'].iloc[i], clean_df['W_PCT'].iloc[i]), 
                 fontsize=6, alpha=0.7)
plt.tight_layout()
plt.show()

# 8. Rebounds vs Win Percentage
plt.figure(figsize=(10, 6))
plt.scatter(clean_df['REB'], clean_df['W_PCT'], alpha=0.7, color='green')
plt.title('Rebounds vs Win Percentage')
plt.xlabel('Rebounds')
plt.ylabel('Win Percentage')
for i, abbrev in enumerate(clean_df['TEAM_ABBREV']):
    plt.annotate(abbrev, (clean_df['REB'].iloc[i], clean_df['W_PCT'].iloc[i]), 
                 fontsize=6, alpha=0.7)
plt.tight_layout()
plt.show()

# 9. Assists vs Win Percentage
plt.figure(figsize=(10, 6))
plt.scatter(clean_df['AST'], clean_df['W_PCT'], alpha=0.7, color='orange')
plt.title('Assists vs Win Percentage')
plt.xlabel('Assists')
plt.ylabel('Win Percentage')
for i, abbrev in enumerate(clean_df['TEAM_ABBREV']):
    plt.annotate(abbrev, (clean_df['AST'].iloc[i], clean_df['W_PCT'].iloc[i]), 
                 fontsize=6, alpha=0.7)
plt.tight_layout()
plt.show()

# 10. Points vs Rebounds
plt.figure(figsize=(10, 6))
plt.scatter(clean_df['PTS'], clean_df['REB'], alpha=0.7, color='purple')
plt.title('Points vs Rebounds')
plt.xlabel('Points Scored')
plt.ylabel('Rebounds')
for i, abbrev in enumerate(clean_df['TEAM_ABBREV']):
    plt.annotate(abbrev, (clean_df['PTS'].iloc[i], clean_df['REB'].iloc[i]), 
                 fontsize=6, alpha=0.7)
plt.tight_layout()
plt.show()

# 11. Points vs Assists
plt.figure(figsize=(10, 6))
plt.scatter(clean_df['PTS'], clean_df['AST'], alpha=0.7, color='red')
plt.title('Points vs Assists')
plt.xlabel('Points Scored')
plt.ylabel('Assists')
for i, abbrev in enumerate(clean_df['TEAM_ABBREV']):
    plt.annotate(abbrev, (clean_df['PTS'].iloc[i], clean_df['AST'].iloc[i]), 
                 fontsize=6, alpha=0.7)
plt.tight_layout()
plt.show()

# 12. Rebounds vs Assists
plt.figure(figsize=(10, 6))
plt.scatter(clean_df['REB'], clean_df['AST'], alpha=0.7, color='brown')
plt.title('Rebounds vs Assists')
plt.xlabel('Rebounds')
plt.ylabel('Assists')
for i, abbrev in enumerate(clean_df['TEAM_ABBREV']):
    plt.annotate(abbrev, (clean_df['REB'].iloc[i], clean_df['AST'].iloc[i]), 
                 fontsize=6, alpha=0.7)
plt.tight_layout()
plt.show()


# Print summary statistics sorted by wins
print("Team Statistics Summary (Sorted by Wins):")
team_summary = clean_df[['TEAM_NAME', 'TEAM_ABBREV', 'W', 'L', 'W_PCT', 'PTS', 'REB', 'AST']].sort_values('W', ascending=False)
print(team_summary)
print(f"\nTotal Teams Analyzed: {len(clean_df)}")
print(f"Average Win Percentage: {clean_df['W_PCT'].mean():.3f}")
print(f"Average Points Scored: {clean_df['PTS'].mean():.1f}")
print(f"Average Rebounds: {clean_df['REB'].mean():.1f}")
print(f"Average Assists: {clean_df['AST'].mean():.1f}")

# Print additional statistics
print(f"\nHighest Win Percentage: {clean_df['W_PCT'].max():.3f}")
print(f"Lowest Win Percentage: {clean_df['W_PCT'].min():.3f}")
print(f"Highest Points Scored: {clean_df['PTS'].max()}")
print(f"Lowest Points Scored: {clean_df['PTS'].min()}")

# Save the cleaned data to CSV for future use
clean_df.to_csv('nba_team_data_clean.csv', index=False)
print("\nCleaned data saved to 'nba_team_data_clean.csv'")
{% endhighlight %}

