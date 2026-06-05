# Khel AI Four-Team T20 Synthetic Dataset

Tournament: Khel AI Champions Trophy 2026

This is a faux but internally consistent cricket dataset generated for the uploaded Django models.py.

## Tournament structure

- 4 teams
- T20 format
- Double round-robin: every team plays every other team twice
- Total matches: 12
- Total innings: 24
- Ball-by-ball scoring follows basic T20 rules:
  - Maximum 20 overs per innings
  - Innings ends at 10 wickets
  - Second innings ends when target is crossed
  - Wides and no-balls are illegal deliveries
  - Byes and leg-byes are legal deliveries
  - Bowlers are capped at 4 overs in the simulated bowling plan
  - Winner and margin are derived from actual innings totals

## Model-aligned CSV files

These match your Django models:

- teams.csv -> Team
- players.csv -> Player
- matches.csv -> Match
- innings.csv -> Innings
- ball_events.csv -> BallEvent
- live_infographic_cards.csv -> LiveInfographicCard

## Extra useful CSV files

- player_attributes.csv: synthetic ratings for model training
- lineups.csv: playing XI and batting order
- innings_scoreboard.csv: innings totals
- batting_scorecards.csv: batter summaries
- bowling_scorecards.csv: bowler summaries
- match_results.csv: winners, margins, player of match
- team_standings.csv: points table
- player_match_features.csv: model training table for player runs/fantasy points
- ball_training_features.csv: model training table for wicket probability/next-ball runs

## Suggested PKL model targets

- player_match_features.csv
  - target_runs
  - target_wickets
  - target_fantasy_points

- ball_training_features.csv
  - target_is_wicket
  - target_total_runs

## Import note

Foreign key columns use the conventional CSV style `team_id`, `match_id`, `innings_id`, `player_id`.
If your importer expects Django's raw field names, map these directly to the FK id values.

This dataset is synthetic and should not be presented as real cricket data.
