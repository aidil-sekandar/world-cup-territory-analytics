# Data Dictionary

This document defines all variables collected for the FIFA World Cup Territory Progression & Attacking Efficiency Tracker.

## Match Information

| Variable       | Definition                                                                         | Type    |
| -------------- | ---------------------------------------------------------------------------------- | ------- |
| stage          | Tournament stage (Group, Round of 32, Round of 16, Quarterfinal, Semifinal, Final) | String  |
| group          | Group designation during group stage (A–L). Leave blank for knockout rounds.       | String  |
| match_no       | Unique match identifier within the tournament dataset                              | Integer |
| date           | Match date                                                                         | Date    |
| team           | Team being analyzed                                                                | String  |
| opponent       | Opposing team                                                                      | String  |
| goals          | Goals scored by team                                                               | Integer |
| goals_conceded | Goals conceded by team                                                             | Integer |

---

## Possession & Progression

| Variable            | Definition                                           | Type    |
| ------------------- | ---------------------------------------------------- | ------- |
| possession          | Percentage of total match possession                 | Float   |
| passes              | Total passes attempted                               | Integer |
| accurate_passes     | Total successful passes                              | Integer |
| final_third_entries | Number of entries into the attacking third           | Integer |
| touches_in_box      | Number of touches inside the opposition penalty area | Integer |

---

## Attacking Output

| Variable          | Definition                                            | Type    |
| ----------------- | ----------------------------------------------------- | ------- |
| xg                | Expected Goals (xG) recorded by SofaScore             | Float   |
| shots             | Total shots attempted                                 | Integer |
| shots_on_target   | Total shots on target                                 | Integer |
| shots_inside_box  | Shots taken from inside the penalty area              | Integer |
| shots_outside_box | Shots taken from outside the penalty area             | Integer |
| big_chances       | Big chances created according to SofaScore definition | Integer |

---

## Final Third Possession

| Variable                     | Definition                                         | Type    |
| ---------------------------- | -------------------------------------------------- | ------- |
| final_third_passes_attempted | Passes attempted in the attacking third            | Integer |
| final_third_passes_completed | Successful passes completed in the attacking third | Integer |

---

## Direct Play

| Variable            | Definition                      | Type    |
| ------------------- | ------------------------------- | ------- |
| long_ball_attempts  | Long balls attempted            | Integer |
| long_ball_completed | Successful long balls completed | Integer |

---

## Defensive Context

| Variable               | Definition                                    | Type    |
| ---------------------- | --------------------------------------------- | ------- |
| recoveries             | Number of ball recoveries                     | Integer |
| interceptions          | Number of interceptions made                  | Integer |
| errors_leading_to_shot | Errors directly resulting in an opponent shot | Integer |
| errors_leading_to_goal | Errors directly resulting in an opponent goal | Integer |

---

# Calculated Metrics

The following variables are not manually collected. They are calculated automatically from raw match data.

| Metric                                      | Formula                                                                  | Interpretation                                  |
| ------------------------------------------- | ------------------------------------------------------------------------ | ----------------------------------------------- |
| FTEE (Final Third Entry Efficiency)         | (Final Third Entries ÷ Passes) × 100                                     | Entries generated per 100 passes                |
| BPE (Box Penetration Efficiency)            | (Touches In Box ÷ Final Third Entries) × 100                             | Percentage of entries reaching the penalty area |
| SCE (Shot Creation Efficiency)              | (Shots ÷ Final Third Entries) × 100                                      | Percentage of entries producing shots           |
| CQ (Chance Quality)                         | xG ÷ Shots                                                               | Average xG generated per shot                   |
| LBE (Long Ball Efficiency)                  | (Long Ball Completed ÷ Long Ball Attempts) × 100                         | Long-ball success rate                          |
| FTPA (Final Third Pass Accuracy)            | (Final Third Passes Completed ÷ Final Third Passes Attempted) × 100      | Passing efficiency in attacking third           |
| TDR (Territory Dominance Ratio)             | Team Touches In Box ÷ Opponent Touches In Box                            | Relative territorial dominance                  |
| WAEI (World Cup Attacking Efficiency Index) | Composite metric combining progression and attacking efficiency measures | Overall attacking efficiency rating             |

---

# Data Source

Primary Data Provider: SofaScore

Collection Method:

* Statistics are collected after full-time.
* One row represents one team's performance in one match.
* Each match generates two rows in the dataset.
* All raw statistics must originate from the same data provider to maintain consistency.
