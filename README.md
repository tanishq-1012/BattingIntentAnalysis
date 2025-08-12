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

## Plot 3

### Boundary % vs Dot Ball % per Batter

Now, let’s analyze each batter’s ability to rotate strike and score boundaries by calculating their Boundary % and Dot Ball %:

<img width="1119" height="511" alt="Screenshot 2025-08-12 at 12 53 43 PM" src="https://github.com/user-attachments/assets/be3fff9f-5ee4-4677-ba3e-6d50c252ca5d" />

PD Salt stands out with the most balanced approach: high boundary rate (~39%) and relatively low dot ball %; indicating consistent attacking intent. TH David, despite a strong boundary presence, also has a high dot ball percentage, reflecting a high-risk, high-reward style.

On the contrary, JM Sharma’s intent appears defensive or ineffective, with a dot ball percentage of over 70% and negligible boundaries. Batters like KL Rahul and V Kohli show moderate boundary rates but also face a significant number of dot balls, suggesting a more conservative or accumulative style of play.

## Plot 4

### Over-Wise Run Progression of Top 4 Batters

Now, let’s track how the top 4 run-scorers progressed throughout the innings by analyzing their over-wise scoring patterns:

<img width="1119" height="511" alt="Screenshot 2025-08-12 at 12 56 30 PM" src="https://github.com/user-attachments/assets/0f3659d5-ddb0-4b2a-833e-d6856b0cc4ed" />

PD Salt demonstrated explosive intent upfront, scoring heavily in the first three overs, especially with a 24-run blitz in the 2nd over. KL Rahul adopted a steadier approach, gradually accelerating through the middle overs and peaking with a 22-run over around the 14th. T Stubbs showed late-inning aggression, particularly in overs 14 to 16, aligning with a finisher’s role. TH David made his impact during the death overs (17–19), consistently scoring above 15 runs per over, indicating high-impact finishing intent.

Overall, each batter’s run pattern reflects their strategic roles in the innings.

## Plot 5

### Correlating Batting Tempo with Wicket Falls

Now, let’s compare how runs and wickets fluctuated over each over to understand momentum shifts during the innings:

<img width="1119" height="511" alt="Screenshot 2025-08-12 at 1 00 08 PM" src="https://github.com/user-attachments/assets/2ae4a84c-3fb4-419f-9678-60bcb6f493c4" />

The early overs (2nd and 3rd) indicate explosive intent, with 35+ runs scored, suggesting aggressive Powerplay batting. However, this high-risk approach also led to early wickets, as seen in the 1st and 4th overs. The middle overs (7–10) show fluctuating intent with moderate scoring and occasional wicket losses, indicating a cautious rebuild phase.

The batting side regained momentum in the death overs (13–19) with consistent scoring around 16–27 runs per over, despite losing wickets in the 14th and 17th, reflecting strong finishing intent while balancing aggression with risk.

## Plot 6

### Batter Profiles Based on Match Performance

Now, let’s build comprehensive performance profiles for each batter, including their strike rate, average, dot ball %, and boundary %:

<img width="899" height="744" alt="Screenshot 2025-08-12 at 1 05 01 PM" src="https://github.com/user-attachments/assets/1d8342e0-a66c-4b1b-924a-a112da10dc3e" />

Here, we started by calculating basic batting stats: total runs, balls faced, and number of dismissals; for each batter. Then, we break down their outcomes into dot balls and boundaries, computing their percentages relative to total deliveries faced. We merged this with the main stats and calculated the batter’s strike rate and batting average.

To maintain statistical significance, we only considered batters who faced at least 10 balls. The resulting batter_profiles dataset gives a well-rounded view of each player’s performance and intent, helping us distinguish between aggressive finishers, anchors, and low-impact players.

So, let’s visualize the performance profiles of the top 4 batters using radar charts to compare strike rate, dot ball %, and boundary %:

The radar charts offer a quick comparative view of batting intent across PD Salt, KL Rahul, T Stubbs, and TH David. PD Salt showcases the most balanced attacking profile, combining a high strike rate, strong boundary %, and moderate dot ball %.

KL Rahul, though maintaining a decent strike rate, relies more on boundaries with relatively higher dot ball involvement, indicating a mixed approach. T Stubbs reflects an explosive style with maximum boundary % and minimal dot balls, ideal for finishing roles. On the other hand, TH David shows a high strike rate but also a high dot ball %, indicating sporadic aggression with a risk of inconsistency.

## 📊 Key Features

### 1. Game Phase Classification
Each ball is tagged with a match phase:
- **Powerplay (0–5 overs)**
- **Middle Overs (6–14 overs)**
- **Death Overs (15–20 overs)**

---

### 2. Batter Strike Rate by Phase
Visualizes how individual batters adapt their intent (strike rate) across different match phases.


---

### 3. Team-Wise Intent Across Phases
Compares team-level strike rates in each game phase.


---

### 4. Boundary % vs Dot Ball %
Bar chart comparison of batters based on how frequently they hit boundaries vs play dot balls.

---

### 5. Over-wise Run Progression
Shows how top-performing batters build their innings over time.

---

### 6. Over-wise Runs vs Wickets
Dual-axis chart showing how scoring rate correlates with wicket loss per over.

---

### 7. Batter Profile Radar Chart
Radar chart showing normalized comparison of:
- Strike Rate
- Dot Ball %
- Boundary %

## Summary

So, by examining strike rates, boundary and dot ball percentages, over-wise run patterns, and wicket impacts, we decoded how each player approached different match phases. From aggressive Powerplay openers like PD Salt to high-impact finishers like T Stubbs and TH David, and steady anchors like KL Rahul, the data revealed distinct batting styles.

1. Understand batting approach based on strike rate by phase.

2. Compare boundary and dot ball percentages across batters.

3. Track run progression over overs.

4. Analyze team strategies in different game stages.

5. Build radar profiles for top batters using normalized metrics.
