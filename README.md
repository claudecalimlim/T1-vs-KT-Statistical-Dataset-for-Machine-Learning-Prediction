# T1-vs-KT-Statistical-Dataset-for-Machine-Learning-Prediction
This repository contains structured and cleaned statistical data from multiple T1 vs KT Rolster matches across the 2025 LCK Season, including Cup, Split, and Road to MSI stages.
The dataset was manually compiled from Liquipedia and processed for predictive modeling and performance analysis. It focuses on both team-level and player-level metrics.

📊 Dataset Overview
Column	Description
Match	Match title and tournament phase
Date	Match date
MatchFormat	Best-of format (Bo3, Bo5, etc.)
Winner	Which team won (T1 or KT)
T1_GameWins	Number of games won by T1
KT_GameWins	Number of games won by KT
T1_KDA	Kills/Deaths/Assists combined across games
KT_KDA	Kills/Deaths/Assists combined across games
T1_Towers, KT_Towers	Total towers destroyed
T1_Barons, KT_Barons	Total Baron kills
T1_Dragons, KT_Dragons	Total Dragon kills
T1_DPM_Avg, KT_DPM_Avg	Average team Damage Per Minute (aggregated)
T1_GPM_Avg, KT_GPM_Avg	Average team Gold Per Minute (aggregated)

💡 Each record represents a full match series (Bo3 or Bo5) with team summaries and average player metrics.

🧠 Purpose

This dataset is designed for:

Machine Learning model training (win prediction)

Team and player performance analytics

Statistical comparison across tournaments

⚙️ Example Use Case (Python/Colab)
import pandas as pd

# Load dataset
url = "https://raw.githubusercontent.com/YOUR_USERNAME/data-of-legends-t1-vs-kt/main/T1_vs_KT_cleaned.csv"
df = pd.read_csv(url)

# View dataset
df.head()

# Example: Predict match winner
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier

X = df[['T1_Towers', 'T1_Barons', 'T1_Dragons', 'KT_Towers', 'KT_Barons', 'KT_Dragons']]
y = df['Winner']

model = RandomForestClassifier().fit(X, y)
print("Prediction Accuracy:", model.score(X, y))

🏅 Credits

Data manually compiled from Liquipedia (2025 season)
Cleaned and structured by Claude Calimlim
Format designed for Colab ML experiments

📘 License

This dataset is shared for educational and research purposes only.
All rights to original match data belong to Riot Games and Liquipedia contributors.
