Task - Olympic Games
Write a JavaScript / C# program to simulate a basketball tournament at the Olympic Games. You will need to simulate both the group stage and knockout stage of the tournament. The task should be done using only JavaScript / C#, without using external packages. The task is executed with the command: npm start / dotnet run and then displays the tournament simulation in the standard output. If you are doing the task in JavaScript, use node v20.17.0, and if you are doing it in C#, use .NET 8. Detailed requirements are given below.
Group Stage Groups and teams are provided in the groups.json file within the task's Git repository. Information includes the country name, ISO-3166 codes, and FIBA rankings before the start of the Olympic Games.
You need to simulate the results of all the group stage matches and rank the teams within each group according to competition regulations. The match results should be determined so that the probability of a team's victory or defeat correlates with the difference in their positions on the FIBA ranking list.
Group Stage Rules: The group stage consists of each team playing against the remaining three teams in their group. Teams receive:
• 2 points for a win,
• 1 point for a draw,
• 0 points for a loss by default.
Teams within a group are ranked based on the number of points. In case two teams from the same group have the same number of points, the result of their head-to-head match will be used as the ranking criterion. If three teams from the same group have the same number of points, the ranking criterion will be the point difference in their head-to-head matches (known as the "circle formation").
At the end of the group stage, the first, second, and third-placed teams from all groups are ranked from 1 to 9:
• The first-placed teams from groups A, B, and C are ranked among themselves primarily by the number of points, then by the point difference (if points are equal), and then by the number of points scored (if points and point difference are equal) to assign ranks 1, 2, and 3.
• The second-placed teams from groups A, B, and C are ranked among themselves by the same principle to assign ranks 4, 5, and 6.
• The third-placed teams from groups A, B, and C are ranked among themselves by the same principle to assign ranks 7, 8, and 9. Teams ranked from 1 to 8 advance to the knockout stage, while the team ranked 9 does not continue in the competition.
In the output, display the results of all group stage matches by rounds, then the rankings within the groups, and which 8 teams have advanced.
Example Output (your display format may differ, but the content should be the same):
Group Stage - Round I:
• Group A:
o Canada - Greece (85:79)
o Australia - Spain (92:80)
• Group B:
o Germany - Japan (97:77)
o France - Brazil (78:66)
• ...
Final Group Standings:
• Group A (Name - Wins/Losses/Points/Points Scored/Points Allowed/Point Difference):
o 
1. Canada 3 / 0 / 6 / 267 / 247 / +20
o 
2. Australia 2 / 1 / 4 / 246 / 250 / -4
o 
3. Greece 2 / 1 / 4 / 233 / 241 / -8
o 
4. Spain 2 / 1 / 4 / 249 / 257 / -8
• ...
Draw: Teams that qualified for the quarter-finals will be divided into four pots:
• Pot D: Teams ranked 1 and 2.
• Pot E: Teams ranked 3 and 4.
• Pot F: Teams ranked 5 and 6.
• Pot G: Teams ranked 7 and 8.
Teams from Pot D are randomly matched with teams from Pot G, and teams from Pot E are matched with teams from Pot F to form the quarter-final pairs. An important rule is that teams that played against each other in the group stage cannot meet in the quarter-finals.
At the same time, semi-final pairs are formed by randomly matching the new quarter-final pairs, with the rule that pairs formed by matching Pot D and E are matched with pairs formed by matching Pot F and G.
After the draw, display the teams by pot and the final structure of the knockout stage.
Example Output:
Pots:
• Pot D
o Germany
o USA
• Pot E
o Serbia
o Canada
• Pot F
o France
o Australia
• Pot G
o Brazil
o Greece
Knockout Stage:
• France - Canada
• Germany - Greece
• USA - Brazil
• Serbia - Australia
Knockout Stage: The tournament continues with the standard elimination format, where winners advance to the semi-finals and losers are eliminated. Winners of the semi-finals go to the final, while losers play for the bronze medal.
Display all knockout stage matches by rounds (quarter-finals, semi-finals, third-place match, final). Then display the teams that won medals.
Example Output:
Quarter-Finals:
• France - Canada (82:73)
• Germany - Greece (76:63)
• USA - Brazil (122:87)
• Serbia - Australia (95:90)
Semi-Finals:
• France - Germany (73:69)
• USA - Serbia (95:91)
Third-Place Match:
• Germany - Serbia (83:93)
Final:
• France - USA (87:98)
Medals:
• 
1. USA
• 
2. France
• 
3. Serbia
Bonus: When determining the probability of winners, also consider the team’s form. The starting point for this calculation can be the data from the exhibitions.json file, which contains the results of 2 friendly matches for each team. Form should be recalculated as the tournament progresses, and you can include the opponent's strength and the point difference achieved by the team as a form factor.

