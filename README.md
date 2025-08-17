# project-final

Final project repo for INFO 523 - Summer 2025.

#### Disclosure:
Derived from the original data viz course by Mine Çetinkaya-Rundel @ Duke University

# Notebooks are where all work was completed

All_Work.ipynb – This notebook contains the complete data processing, feature engineering, exploratory data analysis (EDA), and modeling workflow for the project. It includes loading datasets, merging player IDs, filtering hitting events, generating visualizations such as strike zone heatmaps, boxplots, scatterplots, and training the Random Forest model to predict batted-ball outcomes.

getstatcast.ipynb – This notebook focuses on retrieving and preparing Statcast data for analysis. It handles data acquisition, cleaning, and transformation from Statcast APIs or CSV files, ensuring the datasets are ready for merging with player and pitch-level information in downstream analysis. Credit to user stephen1694 for his code.

# Data
- **[pitch_2024_relevant](data/pitch_2024_relevant.csv)**: Contains all relevant pitch-level data for the 2024 season, including metrics such as pitch type, speed, movement, and plate location.

- **[pitch_2024_top100_reduced](data/pitch_2024_top100_reduced.csv)**: A filtered version of the 2024 pitch dataset containing only the top 100 pitchers by selected criteria, with reduced columns for faster analysis.

- **[player_ids](data/player_ids.csv)**: Maps MLBAM IDs to player names for both batters and pitchers, allowing merging with pitch and batted ball datasets.

- **[BIP_2024_top100](data/BIP_2024_top100.csv)**: Contains balls-in-play data for the top 100 pitchers in 2024, including batted ball metrics such as launch speed, launch angle, and resulting events (singles, doubles, etc.).

## Variable Names and Descriptions:

Column Definitions

- **batter** (int) – MLB Player ID tied to the play event.  
- **game_year** (int) – Year the game took place.  
- **game_date** (date) – The calendar date of the game (YYYY-MM-DD).  
- **home_team** (string) – Abbreviation of the home team.  
- **stand** (string) – Side of the plate the batter is standing.  
- **p_throws** (string) – Hand the pitcher throws with.  
- **pitch_type** (string) – The type of pitch derived from Statcast.  
- **effective_speed** (float) – Speed adjusted based on the pitcher's release extension.  
- **pfx_x** (float) – Horizontal movement in feet from the catcher's perspective.  
- **pfx_z** (float) – Vertical movement in feet from the catcher's perspective.  
- **plate_x** (float) – Horizontal position of the ball when it crosses home plate.  
- **plate_z** (float) – Vertical position of the ball when it crosses home plate.  
- **zone** (int) – Zone location of the ball when it crosses the plate.  
- **description** (string) – Description of the resulting pitch.  
- **launch_speed** (float) – Exit velocity of the batted ball as tracked by Statcast. Estimates included for batted balls not tracked directly.  
- **launch_angle** (float) – Launch angle of the batted ball as tracked by Statcast.  
- **hc_x** (float) – Hit coordinate X of the batted ball.  
- **hc_y** (float) – Hit coordinate Y of the batted ball.  
- **if_fielding_alignment** (string) – Infield fielding alignment at the time of the pitch.  
- **events** (string) – Event of the resulting plate appearance. 