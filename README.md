# dk_nba data dictionary for 2015-2019 pickles


**date:**	Date the game was played

**gmID:**	The unique ID of the game

**playerID:**	The unique ID of the player

**First_Last:**	Player name

**First	Player:** First Name

**Last	Player:** Last Name

**team:**	Team player is on

**opp:**	The opponent for that day

**location:**	This is home (0) or away (1)

**total:**	The total number of points expected, per Vegas Line

**spread:**	The spread of the game, per Vegas Line

**prior_dkp:**	The draftKings points the player scored in the prior game

**dkp_diff:**	The difference in draftkings points the player scored in the last two games, this is intending to get a trend

**three_day_avg:**	The three day average of Draft Kings points

**three_day_avg_diff:**	The difference in three day average of draft kings points, also trying to capture scoring trends

**team_points:**	The points the team scored in the current game

**opp_points:**	The points the opponent scored in the current game

**dkp:**	The draftkings points the player scored in the current game

**dk_sal:**	The salary of the player for the current game

**dk_sal_change:**	the change in salary for the player from the prior game to the current game

**fd sal:**	IGNORE

**rest_day_bucket:**	The number of days rest the player had coming into the current game. (-1) for Null, (0) if it's a back to back game, (1) if there is a day of rest between games, (2) if there 2 days rest, (4) if it's over a week, else it's (3)

**start_flag:**	1 if the player was in the starting lineup, 0 if not

**actv_flag:**	1 if the player was active/available for the game, 0 if not

**pos:**	The position eligibility of the player - can be multiple, (1) point guard, (2) shooting guard, (3) small forward, (4) power forward, (5) center

**min_played:**	The number of minutes the player played

**fgm:**	Field goals made in the game

**fga:**	field goals attempted in the game

**pt:**	pts scored

**rb:**	rebounds

**as:**	assists

**st:**	steals

**bl:**	blocks

**to:**	turnovers

**three_point_attempts:**	

**three_point_made:**

**ftm:**	free throws made

**fta:**	free throws attempted

**off_reb:**	offensive rebounds

**def_reb:**	defensive rebounds

**fouls:**	fouls

**teamfga:**	the field goals the entire team attempted in the game

**teamfta:**	the free throws the team attempted in the game

**teamto:**	the turnovers the team commited in the game

**teamOR:**	the number of offensive rebounds the team had

**teamDR:**	the number of defensive rebounds the team had

**teamFGM:**	the number of field goals made by the team

**oppfga:**	the oppontents field goals made

**oppfta:**	the opponents free throws attempted

**oppto:**	the opponents turnovers

**oppOR:**	the oppontents offensive rebounds

**oppDR:**	the oppontents defensive rebounds

**oppFGM:**	the opponents field goals made

**usage:**	Usage is a metric that shows how much the player was involved. This is important for draft kings - if we could predict usage it would be helpful - derived using: x = 100 * ((df['fga'] + .44 * df['fta'] + df['to']) * (df['tmstMin']/5)) / (df['Minutes'] * (df['tmstfga'] + .44 * df['tmstfta'] + df['tmstto']))

**prior_game_usage:**	The is the usage of the player in the prior game - I wonder how predictive it is of current game usage

**gm_score:**	game score is a metric that judges how well a player played in a game

**prior_game_score:**	prior game game score, I wonder if this is predictive of anything

**possessions:**	number of possessions the team had in the current game; derived using: x = 0.5 * ((df['teamfga'] + 0.4 * df['teamfta'] - 1.07 * (df['teamOR'] / (df['teamOR'] + df['oppDR'])) * (df['teamfga']
        - df['teamFGM']) + df['teamto']) + (df['oppfga'] + 0.4 * df['oppfta'] - 1.07 * (df['oppOR'] / (df['oppOR'] + df['teamDR']))
        * (df['oppfga'] - df['oppFGM']) + df['oppto']))

**ppp:**	points per possession this is a point in time metric - it should indicate how much a team scores

**oppdfeff:**	opponents defensive effciency - this is a metric that judges how good the defense is. It should help identify players in good matchups. It's a rolling calculation throughout the season
