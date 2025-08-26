# Cincinnati Reds Hackathon 2025 Submission

## Overview

This project was a submission I have done individually representing Carnegie Mellon University towards the Cincinnati Reds Hackathon that was held in 2025. The prompt for this year was to predict the amount of opportunity a player would receive in 2024 based on the Statcast data given from 2021~2023. 

I have attempted to use a **LightGBM (LGBM) regressor** in order to solve this problem, as not only is it efficient for solving this particular problem, but also shows which features were important in the prediction.

## Data Analysis and Model Creation

The first step shown in the Jupyter notebook was to get the aggregate **seasonal** data for all players. Because the data provided from Statcast was only composed of pitch-by-pitch data, this conversion was necessary as ultimately seasonal data is more crucial when it comes to determining who to put in the line-up. To further explain this, MLB has 162 games per season, allowing seasonal data to be significantly valuable compared to other sports when it comes to the translation between the results shown on field to the actual ability of the player due to the tremendous amount of data being able to be collected.

Next step was to experiment with different machine learning models to see which performed the best. Although it is not shown in the Jupyter Notebook file, I have attempted to use a Decision Tree Classification algorithm (which significantly underperformed compared to other models), **Elastic Net** model, and **LGBM regressor** model. Elastic net model was chosen as it is effective with handling multicollineraity, which often occurs in baseball statistics. 

Different models were created between batters and pitchers, as their purposes in the game of baseball significantly differ, along with the statistics that are commonly used with each role. After all, batters are the offensive side, and pitchers are the defensive side, and these two terminologies are complete antonyms.

## Results

Ultimately, the **LGBM Regressor** model was chosen due to the easyness of viewing performance and important metrics. The top 5 most important metrics for the batter and pitcher models are shown below:

**Batter model**:
1. *age (in the current season)*
2. *aggregate change in run expectancy (including any runs that were scored through the play)*
3. *K%*
4. *barreled ball ratio*
5. *plate appearances (aggregate of passt 2 years)*

**Pitcher model**
1. *age (in the current season)*
2. *aggregate change in run expectancy (including any runs that were scored through the play)*
3. *number of pitches*
4. *K/BB*
5. *K%*

Clearly we were able to see that **age** and **aggregate change in run expectancy** were key components for both models. Thus, based on these two statistics, it would be helpful for baseball teams to determine which player would deserve more playing time. 
