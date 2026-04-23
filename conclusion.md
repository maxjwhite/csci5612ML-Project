---
layout: page
title: Conclusion
permalink: /conclusion/
---
<img src="{{ site.baseurl }}/image/bulls.png"
     alt="Finals logo"
     style="float: left; width: 35%; margin: 10px 25px 20px 0; border-radius: 10px;">
<p style="text-align: justify;">
This project explored what helps explain success in the National Basketball Association using team performance data, and the most important takeaway is that winning is not driven by a single statistic. Instead, successful teams tend to show strength across many areas of the game at the same time. When teams are consistently good at both offense and defense while also limiting mistakes, they are much more likely to land in the higher win categories, a pattern confirmed by every model tested.
</p>

<p style="text-align: justify;">
One of the clearest findings came from dimensionality reduction, a technique that compresses many statistics down to their most essential signal. When applied here, it revealed that roughly 68% of all the variation across NBA teams is captured by a single underlying dimension, essentially a composite measure of overall efficiency. Net Rating, which tracks how much a team outscores opponents per 100 possessions, sat at the core of that dimension. This means that despite tracking ten different statistics, most of what separates teams comes down to one thing: are you consistently better than the other team when the ball is in play?
</p>

<p style="text-align: justify;">
Teams also naturally fall into clear performance groups. Clustering methods, which find structure in data without being told what to look for, independently and consistently identified three tiers: a small group of elite teams, a large competitive middle, and a struggling bottom tier. These groupings were not forced by the analysis; they emerged on their own across multiple different algorithms, which strengthens confidence that they reflect something real about how the league is structured.
</p>

<img src="{{ site.baseurl }}/image/playoff.png"
     alt="Finals logo"
     style="float: left; width: 35%; margin: 10px 25px 20px 0; border-radius: 10px;">
<p style="text-align: justify;">
A more nuanced finding is that the middle tier was consistently the hardest to classify. Every predictive model made its errors almost exclusively on mid-tier teams. This is not a flaw in the analysis. It reflects a genuine truth: the teams occupying the middle of the league do not have a clear statistical identity. They are neither dominant nor deficient in any obvious way, which makes them harder to evaluate and, in practice, harder to build around.
</p>

<p style="text-align: justify;">

The results also show that different analytical approaches all point to similar conclusions. Whether grouping teams by similarity, building classification models, or mining for statistical patterns through association rules, the same themes appeared repeatedly. Efficient offense, disciplined ball control, and solid defense tend to occur together on winning teams and that combination is more predictive of success than any single standout number.
</p>

<p style="text-align: justify;">
Overall, this project shows that while basketball is complex and dynamic, successful teams share a common foundation. They are well-rounded, consistent, and effective across multiple dimensions of the game. The data does not offer a guaranteed formula, but it does offer a clear signal: teams that perform well across many areas are the ones most likely to reach the top.
</p>
