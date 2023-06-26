---
title: "EdPlace Recommender"
date: "2023-06-23"
draft: true
socialShare: true
---

## EdPlace Recommender

We built the recommender [EdPlace](https://www.edplace.com/) uses to recommend content to students. As this is a commercial project, I can't share details about the data, but I can share the main ideas.

We did exploratory data analysis (EDA) before we set the recommender. Mainly feature selection. We explored the distributions of features and looked into PCA results, co-linearities, and correlations. Unfortunatly, it is not possible to discuss the details of that here.

## The Business Problem

At the time of the project, there were over 100,000 students on EdPlace. They have thousands of worksheets, crafted by experienced teachers accross maths, science, and English. To guide students on their learning journey, **EdPlace recommends a new worksheet to each student**. The old reccomender followed the syllabus. This is a good starting point. However:

1. **The students performance wasn't taken into account**. A struggling student seeing topics for the first time would get identical recommendations to a confident student who has covered similar material at school.
2. **The order was fixed, and imposed by teachers**. It couldn't learn and adapt from paths or connections discovered by students.
3. **This is a one size fits all solution**. Individual differences aren't taken into account.

## The Technical Problem

### What is the best worksheet?

In the case of a film recommender, viewers can rate films. The more stars (from similar users - we'll return to this) the more likely you should recommend the film. This gives a **clear target**. Having a target is the difference between supervised and unsupervised machine learning.

Ratings don't have the same meaning for worksheets. We needed to **define a target**. We decided that **score** was the best signal we had. However, if we made high score the target, we would only recommend easy worksheets. If low score was the target, students would only get difficult worksheets. We needed something in between.

This problem reminded me of [a paper I had read (Wilson et al, 2019)](https://www.nature.com/articles/s41467-019-12552-4). They observe that the optimal accuracy of optimal training is about 85 %. The paper uses artificial neural networks, but does provide references to human and animal learning. In figure 5, they relate this to the model of flow - a well known concept in popular culture. I recreated a schematic here:
