# 🏏 Batting Intent Analysis – IPL Match

This project explores **batting intent** in a single IPL match (ID: `1473461`) by analyzing player and team-level performance across different phases of the game. Using **Python**, **pandas**, and **Plotly**, we visualize how batters approach different game situations based on strike rate, boundary percentage, dot ball percentage, and other key metrics.
In modern T20 cricket, especially in high-stakes tournaments like the IPL, understanding a batter’s intent is as important as analyzing their strike rate or total runs. Batting intent reflects how aggressively a player approaches different phases of the game.

# Batting Intent Analysis in IPL 2025: Overview

We’ll be using ball-by-ball data from a recent IPL match between RCB and DC, which includes details like over number, batter, bowler, runs scored, and wicket events. This rich, granular dataset allows us to analyze batting patterns across different phases of the game.

The scope of our analysis is to understand batting intent: how players approach the game in various situations; by examining strike rates, boundary percentages, dot ball rates, and over-wise performance, ultimately uncovering insights that can influence real-time strategy and decision-making.

## 📂 Dataset

- **Source:** IPL Match Deliveries CSV
- **File:** `ipl_match_1473461_deliveries.csv`
- **Key Columns Used:** `batter`, `team`, `over`, `runs_batter`, `player_out`

<img width="1149" height="398" alt="Screenshot 2025-08-12 at 12 42 05 PM" src="https://github.com/user-attachments/assets/73915b66-58d8-46ec-b80c-ca3fdc029783" />

<img width="1149" height="231" alt="Screenshot 2025-08-12 at 12 42 21 PM" src="https://github.com/user-attachments/assets/eac88444-e9ae-4774-b4c3-3afe4cf83b09" />

let’s categorize each delivery into match phases: Powerplay, Middle Overs, and Death Overs; based on the over number:

<img width="717" height="367" alt="Screenshot 2025-08-12 at 12 47 08 PM" src="https://github.com/user-attachments/assets/5276944b-4fb2-4e52-aa3f-9c27c8ad79ec" />

Here, we defined a function get_phase() that assigns a phase label based on the over number: overs 0 to 5 as Powerplay, 6 to 14 as Middle Overs, and 15 onwards as Death Overs. Then, we applied this function to the over column to create a new phase column in the dataset.

## Plot 1

<img width="1119" height="511" alt="Screenshot 2025-08-12 at 12 49 40 PM" src="https://github.com/user-attachments/assets/0f6cdfea-4de4-48bd-abfa-7a3ecc5af11d" />

T Stubbs and KL Rahul showcased aggressive intent in the Death Overs, with strike rates exceeding 220 and 220, respectively, indicating high-impact finishing roles. PD Salt and AR Patel were strong starters with strike rates over 140 in the Powerplay.

## Plot 2

### Team-Wise Batting Intent Across Match Phases

Now, let’s compare the batting intent of both teams across different match phases using strike rate as a metric:

<img width="1119" height="511" alt="Screenshot 2025-08-12 at 12 51 25 PM" src="https://github.com/user-attachments/assets/4ff5f83a-7d27-43f5-81fb-49e83cb82e95" />

The graph reveals a stark contrast in batting intent between Delhi Capitals and Royal Challengers Bengaluru across different match phases. Delhi Capitals showed a clear surge in aggression during the Death Overs, registering a strike rate close to 240, significantly outpacing RCB.

In contrast, RCB were more aggressive in the Powerplay with a strike rate of around 135, while Delhi started more cautiously. Across Middle Overs, Delhi again maintained a higher tempo than RCB, suggesting better momentum-building and acceleration strategies. Overall, DC dominated the later stages, while RCB leaned on early aggression.
