# NHL Psychological Footprint: Behavioral Analysis Under Pressure

A data science pipeline designed to measure the "Psychological Footprint" of NHL playoff pressure. This project compares how the core cohorts of the **Detroit Red Wings** and **Montreal Canadiens** react to high-leverage standings pressure using behavioral proxy metrics.

## 🚀 The Challenge: Data Engineering in the Dark
This project features a robust, custom-built ETL pipeline that addresses several real-world data engineering challenges:
* **API Resiliency:** Bypassed the deprecated `nhl-api-py` wrapper to hit the native NHL Web API directly.
* **Firewall Evasion:** Implemented a `urllib` native Python networking stack with browser-spoofing (User-Agent masking) to prevent server-side bot-blocking.
* **Schema Evolution:** Navigated a silent API change where the NHL stripped EDGE telemetry from public endpoints, requiring a strategic pivot to behavioral proxies (Shots on Goal & Blocked Shots).

## 🏒 Methodology
The analysis isolates "High Leverage" games using the following strict filters to eliminate noise:
* **Standings Gap:** Points percentage difference of $\le 0.06$ between opponents.
* **Schedule Fatigue:** Minimum of 1 rest day to control for back-to-back performance dips.
* **Score Effects:** Removal of blowouts ($\ge 5$ goal differential) to ensure high-intensity gameplay.
* **In-Conference Only:** Focuses exclusively on games with direct playoff implications.

## 📊 Key Findings: "The Diverging Cores"
While traditional sports media suggests players "choke" or "grip the stick tight" under pressure, this analysis found a fascinating divergence:
* **Montreal Canadiens (The Turtle Shell):** Observed a 63% spike in blocked shots and a drop in shot volume, validating the "defensive collapse" narrative.
* **Detroit Red Wings (The Attackers):** Exhibited an offensive surge, increasing shots on goal while abandoning defensive shot-blocking.
* **Statistical Rigor:** Welch’s t-tests were applied to both cohorts to distinguish between seasonal noise and meaningful behavioral shifts.

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Libraries:** Pandas, Scipy (Welch's T-Test), Seaborn, Matplotlib, Urllib (Native Networking)
* **Data Source:** NHL Web API (Gamecenter/Boxscore)
