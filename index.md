---
layout: page
title: Introduction
permalink: /
---
<img src="https://images.unsplash.com/photo-1546519638-68e109498ffc?auto=format&fit=crop&w=1600&q=80"
     alt="Wide-angle view of a professional basketball game"
     style="float: right; width: 45%; margin: 0 0 20px 25px; border-radius: 10px;">
<p style="text-align: justify;">
The National Basketball Association (NBA) is one of the most popular and closely followed professional sports leagues in the world, attracting fans, analysts, media organizations, and team decision-makers alike. Beyond entertainment, the NBA has become a space where data plays an increasingly important role in shaping how the game is understood and discussed. Every season, thousands of games generate loads of data on player performance, team outcomes, and league-wide trends. This data helps frame conversations about success, improvement, and competitive balance across the league. For fans, data-driven insights provide deeper context for what happens on the court. For teams and players, performance statistics can influence evaluations, contracts, and career trajectories. As analytics becomes more visible in sports coverage, it is important to understand what stories the data can meaningfully tell. Basketball’s structured gameplay and consistent rules make it especially well-suited for systematic analysis. Examining NBA data allows us to explore broader questions about performance and consistency in a familiar setting. This project focuses on analyzing NBA data to better understand patterns that emerge across players, teams, and seasons.
</p>

<p style="text-align: justify;">
The data used in this project is gathered from publicly available NBA statistics accessed through the <a href="https://github.com/swar/nba_api" target="_blank">nba_api</a>, a community-supported repository that provides structured access to official league data. This source aggregates historical and current information that is commonly referenced in media coverage and public discussions of the NBA. Over the past decade, analysts and researchers have used similar data to study topics such as scoring trends, efficiency, and the impact of individual players. While professional teams often rely on proprietary tools, public NBA data offers a valuable opportunity for independent exploration. However, raw statistics do not always tell a complete story without interpretation. Context, comparison, and variation across seasons all influence how the data should be understood. By examining NBA data from multiple perspectives, this project aims to clarify how performance patterns develop over time. The goal is not to predict outcomes, but to better interpret what the available data reveals. Ultimately, this project seeks to shed a bit more light on what makes a Championship team in the NBA. 
</p>

<img src="image/finals.png"
     alt="Finals logo"
     style="float: left; width: 35%; margin: 10px 25px 20px 0; border-radius: 10px;">
<p style="text-align: justify;"> To accomplish this, the project will apply a combination of dimensionality reduction and pattern-discovery techniques, specifically principal component analysis (PCA), association rule mining (ARM), and multiple clustering methods including k-means, hierarchical clustering, and DBSCAN. PCA will first be used to reduce the dimensionality of the dataset by identifying a smaller set of components that capture the majority of variation across team performance metrics. This helps simplify interpretation while preserving the most important statistical structure in the data. Clustering methods will then group teams or seasons based on similarity in their statistical profiles. K-means will provide clearly defined partitions of teams into distinct groups, hierarchical clustering will allow us to examine nested relationships and similarities at different levels of granularity, and DBSCAN will help identify dense groupings while also detecting potential outliers that do not fit common team archetypes. Finally, association rule mining will be used to uncover combinations of performance characteristics that frequently occur together, particularly among high-performing or championship teams. By integrating PCA for structure, multiple clustering techniques for segmentation, and ARM for relationship discovery, this project aims to provide a comprehensive view of the statistical patterns that consistently align with elite performance in the NBA. 
</p>

<div style="clear: both;"></div>

<p style="text-align: justify;"> From a basketball perspective, this project highlights how teams tend to group together based on overall style and effectiveness of play rather than any single statistic. Strong teams consistently show a balance of efficient offense, solid defense, and good decision-making, which naturally places them in similar clusters. On the other hand, lower-performing teams often share struggles across multiple areas, leading them to group together as well. This reinforces the idea that success in the NBA is not driven by one factor alone, but by a combination of strengths that work together over the course of a season. Given that there are multiple different contributing factors to consider as it relates to win prediction, it is appropriate to explore and use multiple different model types. This ensures that we are casting a broad net accross our data and exploring as many aspects of it as possible. 
</p>

<p style="text-align: justify;">
To build on these earlier approaches, this project also considers how more advanced predictive techniques can help deepen our understanding of team success in the National Basketball Association. Methods such as support vector machines and ensemble models provide a different perspective by focusing on how well patterns in the data can distinguish stronger teams from weaker ones. Rather than grouping teams or identifying common characteristics alone, these approaches evaluate how combinations of performance metrics relate to overall success in a more structured way. Ensemble methods, in particular, bring together multiple models to form a more balanced and reliable view, helping reduce the limitations of any single approach. While these techniques are often used for prediction, in this project they serve a broader purpose: reinforcing and validating the patterns observed through earlier analysis. By combining insights from clustering, dimensionality reduction, association patterns, and these additional modeling strategies, the project offers a more complete and well-rounded interpretation of what defines high-performing teams. This layered approach helps ensure that conclusions are not driven by one method alone, but instead reflect consistent trends that appear across multiple perspectives on the data.
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
