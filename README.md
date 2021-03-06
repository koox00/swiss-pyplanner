# Swiss Tournament Planner

Python module that uses the PostgreSQL database to keep track of players and matches in a swiss game tournament.

# Table of Contents

- [Installation](#instalation)
- [Details](#hot_it_works)

# Installation <a id="instalation"></a>

First create a database called **tournament**. Then run the queries in the `tournament.sql` file.
These queries will create three *tables*, **players**,  **matches** and a *mapping table* between the two called **players_to_matches** and an *sql view* called **player_standings**.
The view contains the player id's along with data about wins and number of matches.

You can run tests located in `tournament_test.py`.

# Details



>A Swiss-system tournament is a tournament which uses a non-elimination format. There are several rounds of competition, but considerably fewer rounds than in around-robin tournament, so each competitor (team or individual) does not play every other competitor. Competitors meet one-to-one in each round and are paired using a predetermined set of rules designed to ensure that as far as possible a competitor plays competitors with the same current score, subject to not playing the same opponent more than once. The winner is the competitor with the highest aggregate points earned in all rounds.-- <cite>[wikipedia.com][1]</cite>

[1]:http://en.wikipedia.org/wiki/Swiss-system_tournament

The module currently supports one tournament per time.
If the number of players are odd numbered one random player every round gets a bye round, which means a free win.
No player can have more than one bye round throughout the tournament.

# TODO

- Support games where a draw (tied game) is possible.
- When two players have the same number of wins, rank them according to OMW (Opponent Match Wins).
- Support more than one tournament in the database.
