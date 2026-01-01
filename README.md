# 🏀 The NBA 3-Point Revolution (1997-2017)

 ### **Project Overview**
This project provides a comprehensive data-driven analysis of how the 3-point shot transformed the NBA over two decades. The study was conducted using a robust dataset consisting of **24,691 rows and 53 columns**, covering extensive player statistics across multiple eras.

To extract meaningful insights, **I personally managed the entire data lifecycle**, including:
* **Data Cleaning & Wrangling:** I cleaned the raw dataset by handling missing values, removing noise, and ensuring data integrity across 20 seasons of statistics.

  
  **Scripting Logic (Python):**
```python # 1. Data Cleaning: Handling missing values and filtering for significance
df = df.dropna(subset=['3PA'])
df = df.fillna(0)

# Filtering for players with more than 10 games and 100 minutes to ensure data quality
df = df[(df['G'] > 10) & (df['MP'] > 100)]

# 2. Initial Cleaning for 1997-2017 and Trade Duplicates
df_all = df[(df['Year'] >= 1997) & (df['Year'] <= 2017)].copy()

# Removing duplicate entries for players traded during the season (keeping the 'TOT' or first entry)
df_all = df_all.drop_duplicates(subset=['Player', 'Year'], keep='first')
```
* **Advanced Data Processing:** I processed and transformed the data to calculate key performance metrics, such as seasonal averages and positional accuracy trends.
* **Statistical Analysis:** I analyzed the shift in offensive strategies and player roles, focusing on the relationship between shooting volume and efficiency.

## The Mission
The primary goal was to investigate the correlation between the exponential growth in 3-point attempts and league-wide shooting accuracy. Specifically, the project examines:

 * **The Volume-Efficiency Balance**: Did the massive surge in attempts lead to a decline in accuracy, or did player skills evolve to meet the demand?

* **Positional Impact**: How did the revolution affect specific positions? A key focus of this analysis is the transformation of "Big Men" (Power Forwards and Centers) from interior scorers to modern perimeter threats.




## Visualizations

### 1. Average 3-Point Attempts
*Annual growth of 3-point attempts per player, showing the steady rise in long-range shooting.*

<img width="750" height="400" alt="AVG of 3PT Attemps" src="https://github.com/user-attachments/assets/ee96aa7a-dee3-447c-9673-9c88ea082827" />

**This visualization highlights the relentless expansion of the 3-point shot. 
Beyond the 1999 lockout anomaly, we see a consistent rise in volume, specifically accelerating after 2012.
This trend confirms that the "3-point revolution" is a league-wide strategic transformation, not just a passing phase.**




### 2. Average 3-Point Accuracy
*Tracking league-wide shooting percentage, demonstrating improved efficiency over two decades.*

 <img width="750" height="400" alt="AVG of 3PT Accuracy" src="https://github.com/user-attachments/assets/d4ff0dcd-d7fd-4bec-83f1-2cd4965940c2" />

**This graph dispels the myth that higher volume leads to lower quality.
Despite the massive increase in attempts, NBA players significantly improved their shooting efficiency, reaching a league-wide accuracy peak by 2017.
This indicates a fundamental evolution in player training and offensive decision-making.**


### 3. Volume vs. Accuracy
*A dual-axis chart showing the explosion in 3PA volume vs. stable league-wide accuracy (1997-2017).*

 <img width="750" height="400" alt="3PT Revolution" src="https://github.com/user-attachments/assets/7a749771-4811-4c42-af5e-535583517dbd" />




### 4. Positional Evolution
*Comparison of 3PT% by position, highlighting the massive leap in accuracy for Power Forwards and Centers.*

<img width="750" height="400" alt="Position Analysis" src="https://github.com/user-attachments/assets/92ae375f-20fe-4848-ba8c-8ad2676a941d" />

**This chart visualizes the true "revolution".
While Guards (PG/SG) have always been efficient shooters, the most significant leap occurred among Big Men.
Between 2007 and 2017, Power Forwards and Centers nearly doubled their effectiveness from deep, reflecting the modern NBA strategy of floor spacing and the rise of the "Stretch-Big".**





### 5. Career Accuracy Leaders
*Top 10 most accurate 3-point shooters (min. 500 attempts) during the 1997-2017 era.*
 <img width="750" height="450" alt="The Influencers" src="https://github.com/user-attachments/assets/2f34c64c-498e-4675-b04f-ae63990563fd" />

**This graph highlights the 10 most accurate 3-point shooters specifically during the 1997-2017 era,led by Stephen Curry with a 43.78% success rate. 
By focusing on this 20-year period and including only players with over 500 attempts, we ensure these results reflect sustained skill within this timeframe.** 



**These elite shooters, like Steve Nash and Kyle Korver, proved that shooting more 3-pointers is the smartest way to win.
Their consistency over 20 years forced teams to change their defense and turned the NBA into a game driven by data and efficiency.**



### 6. Identifying Player Styles using Machine Learning

In this part of the project, I wanted to see if the data could tell me which "type" of shooter each player is, regardless of their official position. To do this, I used a **Machine Learning** algorithm called K-Means Clustering.

First, I used a tool called the "Elbow Method" to figure out the best way to group the players, and it showed that 3 groups was the perfect number. Then, I let the model analyze two main things: how many shots a player took (Volume) and how accurate they were (Efficiency).

The results were really interesting, the model automatically sorted everyone into three clear "Archetypes": Elite Superstars (high volume and high accuracy like Stephen Curry), High-Accuracy Snipers (very accurate but fewer shots), and Steady Contributors (the reliable role players). This shows how machine learning can find patterns in basketball that we might miss just by looking at basic averages. 


<img width="750" height="450" alt="K-FIND" src="https://github.com/user-attachments/assets/be7ecf31-92b6-48b7-9a5b-963136fbaecc" />



**The "Elbow" Point**: Looking at the generated Elbow Curve, the rate of decrease in WCSS drops significantly after K=3. This point represents the "elbow," where adding more clusters no longer provides substantial improvement in explaining the data.




<img width="750" height="450" alt="K_MEANS" src="https://github.com/user-attachments/assets/fcaff689-7714-4a26-813d-6f22193e5e74" />

### The Archetypes Identified:

**Elite Superstars (Green):** These are the league's primary offensive engines. This cluster includes legends like Ray Allen and Stephen Curry, who maintain high accuracy despite extreme volume (4,000+ attempts).

**High-Accuracy Snipers (Orange):** Players who specialize in precision. They occupy the top-left of the chart, maintaining elite percentages (often above 38%) but with lower career volume compared to the Superstars.

**Steady Contributors (Blue):** This group represents the foundation of the league's spacing.
They provide reliable perimeter shooting at a moderate volume, typically ranging between 30% and 35% accuracy.




 
## Key Insights
### 1. The Volume-Efficiency Paradox (Volume vs. Accuracy)
The data reveals a groundbreaking shift in offensive philosophy. Historically, coaches feared that increasing shooting volume would naturally lead to a decline in efficiency (the "Law of Diminishing Returns").

**Skill Scaling**: Despite average 3-point attempts per player skyrocketing by nearly 50% between 1997 and 2017, shooting accuracy did not plummet.

**The Analytical Shift**: Post-2012, we observe a sharp acceleration in attempts. 
This indicates that the league moved from using the 3-pointer as a "last resort" to making it a primary tactical weapon, backed by players who trained specifically to maintain high efficiency at high volumes.


 **Scripting Logic (Python):**
```python # 1. Prepare Data - 1997-2017, Clean Trades
df_final = df[(df['Year'] >= 1997) & (df['Year'] <= 2017)].copy()
df_final = df_final.drop_duplicates(subset=['Player', 'Year'], keep='first')

# 2. Calculate Pct for ALL players (handling division by zero)
df_final['3P_Pct'] = df_final['3P'] / df_final['3PA']
df_final['3P_Pct'] = df_final['3P_Pct'].fillna(0) # Fill 0 for players with no attempts

# 3. Aggregate - MEAN for ALL players
# This will match your first graph where 2017 is around 140
combined_all = df_final.groupby('Year').agg({
    '3PA': 'mean',
    '3P_Pct': 'mean'
})
``` 

### 2. The Positional Revolution: Rise of the "Stretch-Big"
This analysis highlights the extinction of the traditional, "low-post only" big man.

**PF & Center Evolution**: Power Forwards and Centers showed the most staggering improvements. In 1997, Centers were virtually non-existent on the perimeter (approx. 12% accuracy); by 2017, their accuracy reached nearly 15% with a significant increase in attempts.

**Power Forward Breakthrough**: PFs transitioned from mid-range shooters to elite threats, with their 3P% jumping from 18% in 2007 to nearly 28% in 2017. This shift forced defenses to "stretch" out to the perimeter, fundamentally altering NBA defensive schemes and court spacing.


 **Scripting Logic (Python):**
```python # 1. Re-defining the clean data for positions
df_pos_acc = df[(df['Year'] >= 1997) & (df['Year'] <= 2017)].copy()
df_pos_acc = df_pos_acc.drop_duplicates(subset=['Player', 'Year'], keep='first')

# 2. Clean positions (
df_pos_acc['Pos_Clean'] = df_pos_acc['Pos'].str.split('-').str[0]

# 3. Calculate 3P% and handle missing values
df_pos_acc['3P_Pct'] = df_pos_acc['3P'] / df_pos_acc['3PA']
df_pos_acc['3P_Pct'] = df_pos_acc['3P_Pct'].fillna(0)

# 4. Filter specifically for 1997, 2007, and 2017 to show the evolution
years_to_show = [1997, 2007, 2017]
df_comparison = df_pos_acc[df_pos_acc['Year'].isin(years_to_show)]

# 5. Create the Pivot Table for the Bar Chart
# Rows: Positions, Columns: Selected Years
pos_bar_data = df_comparison.pivot_table(index='Pos_Clean', columns='Year', values='3P_Pct', aggfunc='mean')
 ``` 

### 3. Elite Performers & The Strategic Milestone
The ranking of the top 10 shooters is not just a list of names; it is a testament to the "Mathematical Optimization" of the game.

**The Curry Standard**: Led by Stephen Curry (43.78%), these elite shooters proved that a 3-point shot at 40%+ accuracy is statistically superior to almost any 2-point attempt.

**Theory to Reality**: The career consistency of legends like Hubert Davis (43.54%) and Steve Nash (42.78%) provided the "proof of concept" that analytics departments needed.
Their evolution represents a major milestone in basketball history-shifting the game from an intuition-based sport to a strategy-led, efficiency-optimized competition.


 **Scripting Logic (Python):**
```python   # 4. Set a minimum threshold to ensure they are consistent shooters
  # ( at least 500 attempts over 20 years)
  min_attempts = 500
  top_shooters = career_stats[career_stats['3PA'] >= min_attempts].copy()

  #  Sort by percentage and take the top 10
  top_10_shooters = top_shooters.sort_values(by='3P_Pct', ascending=False).head(10)
 ``` 
### 4. The "Unstoppable" Tier (Volume + Efficiency):
Usually, the more a player shoots, the less accurate he becomes because of fatigue and better defense. Our model found a small group of "Elite Superstars" like Stephen Curry and Ray Allen who break this rule, 
they shoot more than anyone else but still keep an incredibly high percentage.

***Specialists vs. Stars:*** The model showed a clear gap between "Snipers" and "Stars".
The High-Accuracy Snipers have the highest percentages, but they only shoot when they are open. 
The Superstars, however, take much harder shots and carry the team's offense, which is why the model put them in their own unique category.

## Spatial Analysis: The 3-Point Revolution in Heatmaps

To truly understand how the NBA has changed, I visualized the spatial distribution of every shot taken in the league during two pivotal seasons: 2003-04 and 2022-23.

### Methodology
* Data Sourcing: Shot coordinates (LOC_X, LOC_Y) were extracted directly from the NBA Stats API using the nba_api library.
* Visualization: I used a Hexbin plot to aggregate thousands of shots into density-based hexagonal bins.
* Logarithmic Scaling: A Log Scale (10^0, 10^1, 10^2) was applied to the color intensity. This ensures that the high volume of shots at the rim doesn't "wash out" the activity along the 3-point line, allowing for a clear view of patterns in both high and low-volume areas.

### What are we looking at?
* Brighter colors (Yellow): Represent high-frequency shot zones.
* Darker colors (Purple/Black): Represent areas where shots are rarely or never taken.

<img width="2103" height="985" alt="HEAT MAPS" src="https://github.com/user-attachments/assets/abd56ef9-2eb9-485a-af12-e4c6f8651c82" />


### Key Insights and Findings

#### 1. The Extinction of the Mid-Range
* 2003-04: The map is filled with orange and red across the mid-range area (between the paint and the arc), showing that the long 2-pointer was a staple of NBA offenses.
* 2022-23: This same area is now a dead zone (black/dark purple). Modern analytics have led teams to abandon these inefficient shots in favor of higher-value opportunities.

#### 2. The Total Perimeter Takeover (Volume, Range and Role)
The modern heatmap reveals a massive shift in how the 3-pointer is utilized across the league:
* Volume: A continuous, bright yellow "Ring of Fire" has formed along the arc, showing that 3-point shooting has transitioned from a specialty to a league-wide requirement.
* Increased Range: The heat in 2022-23 extends significantly further back from the line, visualizing how players are now comfortably taking shots from several feet behind the arc (The "Curry Effect").
* Positional Evolution: The increased density at the top of the key and the wings highlights that all five positions, including big men, are now integrated into the perimeter offense.

#### 3. Offensive Polarization
* The 2022-23 map shows a highly polarized offense: teams either attack the rim (the brightest spot) or shoot the three. 
* The middle ground has been sacrificed for statistical efficiency, creating a game that is played almost exclusively at the two highest-value zones on the court.

## Final Research- Correlations & Prediction
### This Final Research is built upon a comprehensive database of NBA team statistics, covering every franchise's performance from the 2000-01 season through the 2023-24 season. The dataset includes critical metrics such as Win Percentages (W/L%), 3-Point Attempts (3PA), 3-Point Percentage (3P%), and overall field goal distributions.

By leveraging this 24-year historical record, the research focuses on three primary objectives:

* **Correlation Analysis:** Quantifying how the relationship between perimeter volume and winning success has shifted across different eras. We analyze whether shooting more 3s still provides the same competitive "edge" today as it did two decades ago.

* **Performance Profiling**: Identifying "Elite Outliers". the specific teams that mastered the balance between high-volume shooting and championship-level winning percentages.

* **Future Trajectory Modeling:** Utilizing Machine Learning (Linear Regression) to project the league's tactical future. By understanding the past growth, we aim to forecast the "periphery-saturation point" of the NBA through the year 2034.

**1. The Era Correlation Shift (Three-Panel Scatter Plot):**
This visualization breaks down the history into three eras: the "Early 2000s," the "Curry Surge," and the "Modern Era."

**What we see**: Each era shows the league's "cloud" of data points moving significantly to the right. In the early 2000s, 15 attempts per game was the norm; today, it is over 35.

<img width="850" height="400" alt="Correlation1" src="https://github.com/user-attachments/assets/0a767e5d-1cd1-46f5-bbfe-0bcadc2592c1" />
<img width="850" height="500" alt="Correlation3" src="https://github.com/user-attachments/assets/f0c2fc98-14c7-442c-9fb9-e4bab71543d7" />

**The Insight**s:
The Volume Paradox: While the volume of shots increased, the correlation between how many shots you take and winning has actually flattened in the modern era.

**Baseline Requirement**: Shooting 3s is no longer a "secret weapon" that guarantees a win; it has become a "barrier to entry." If you don't shoot high volume, you cannot compete, but shooting high volume alone doesn't ensure success.

## Data Processing & Elite Team Selection
To understand the pinnacle of the "Three-Point Revolution," I didn't just look at who shot the most. I performed a targeted data cleaning and filtering process to identify the 5 most efficient winning teams in modern history.
The Cleaning Process:
 * Removing Noise: I filtered out all "League Average" and "League Total" rows from the database to ensure the analysis focused strictly on individual team performances.

 * Handling Missing Values: I cleaned the dataset from any null values in the 3-Point Percentage and Win Percentage columns to maintain statistical integrity.

 * The "Elite" Filter: To find the true masters of the game, I set a strict performance threshold:
  only teams with a Win Percentage of 60% or higher (equivalent to a 55+ win season) were considered.
  This ensured we were looking at championship-caliber teams, not just high-volume shooters.

* Ranking by Precision: From this elite group, I selected the Top 5 teams with the highest 3-Point Percentage (3P%).
  <img width="800" height="500" alt="Lollipop-NBA" src="https://github.com/user-attachments/assets/31407d02-7e52-4ee7-aeda-89c993f12614" />
### What this Graph Represents:
The resulting Vertical Lollipop Chart is a visual proof of the 3-point revolution's impact. It shows that at the highest level of professional basketball, there is a direct link between "Elite Precision" and "Elite Winning."

The Findings: By isolating these 5 teams (like the 2016 Warriors and the 2001 Spurs), we can see that they didn't just follow the trend—they led it. Their ability to maintain near 40% accuracy while winning over two-thirds of their games highlights how the 3-pointer became the most lethal weapon in the NBA arsenal.



## Future Forecasting (Machine Learning & Regression Analysis)
To conclude the research, I moved beyond historical analysis into the realm of Machine Learning. The goal was to determine if the 3-point revolution has reached its peak or if the league will continue to trend toward the perimeter over the next decade.

Methodology:
I utilized a Linear Regression model, a fundamental Machine Learning algorithm, to identify the underlying growth trend in the NBA.

* **Data Aggregation**: I calculated the annual league-wide average of 3-point attempts (3PA) per game from 2000 to 2024.

* **Model Training**: The model was trained to recognize the "pace of change" over the last 24 years, effectively mapping the correlation between time (years) and shot selection (volume).

* **Forecasting**: Once the model learned the historical trajectory, I used it to predict the shooting volume for the next 10 years, up to the 2033-34 season.

  <img width="900" height="700" alt="2034 Forcast" src="https://github.com/user-attachments/assets/61750c02-4d89-46fb-9a9f-52daf4b8f780" />


**What the Graph Show**s:
The visualization features a Unified Forecast Plot:

* Historical Data (Blue): Represents the verified stats from the past two decades.

* The Regression Line: A mathematical "best-fit" line that smooths out year-to-year fluctuations to show the true direction of the league.

* The 10-Year Forecast (Red): The projected growth, highlighting a consistent and relentless climb in 3-point volume.

 ### The Future of the NBA
The core insight from this Machine Learning model is profound: The 3-point revolution is not slowing down. 
* The 46.2 Milestone: The model predicts that by 2034, teams will average over 46 attempts per game.
* Tactical Saturation: This indicates that the NBA is moving toward a future where nearly half of all offensive possessions will conclude with a 3-point shot.



---


### Conclusion
**This project shows that the NBA's 3-point revolution is much more than just taking more shots, it is a complete change in how basketball is played. By using K-Means clustering to see how player roles changed, era-based correlations, and Machine Learning to predict the future, the data proves that what used to be a "special weapon" is now a basic requirement to win. My analysis reveals that the game has fundamentally changed, moving toward a future where shooting from deep is the most important part of a team's strategy and the main key to success in the modern NBA.**




## Tools & Technologies
* **Python**: Integrated **Pandas**, **Scikit-Learn**, **Matplotlib**, and **Seaborn** for the complete data science pipeline, from cleaning and K-Means clustering to advanced spatial visualizations.
* **NBA API**: Sourced real-time, high-fidelity shot coordinates and historical player data directly from official NBA servers.
* **Kaggle**: Leveraged a large-scale historical database for comprehensive long-term trend analysis.
* **Google Gemini AI**: Used for code optimization, complex problem-solving, and professional data storytelling.
* **Google Colab**: Cloud-based development environment used for writing and executing the Python code.
* **Microsoft Excel**: Utilized for initial data exploration, quick filtering, and raw dataset validation.
## 🚀 Run the Code
You can view, edit, and run the complete Python analysis directly in Google Colab:
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1ieHkvKSqAvy6_-5tlm4BO7ZWnxCdd5u-#scrollTo=UrxrQu8GONrg)
