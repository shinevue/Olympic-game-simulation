# Task - Olympic Games

## Description

Write a JavaScript / C# program to simulate a basketball tournament at the Olympic Games. You will need to simulate both the group stage and knockout stage of the tournament. The task should be done using only JavaScript / C#, without using external packages. The task is executed with the command: `npm start` / `dotnet run` and then displays the tournament simulation in the standard output. If you are doing the task in JavaScript, use node v20.17.0, and if you are doing it in C#, use .NET 8. Detailed requirements are given below.

## Group Stage

Groups and teams are provided in the `groups.json` file within the task's Git repository. Information includes the country name, ISO-3166 codes, and FIBA rankings before the start of the Olympic Games.

You need to simulate the results of all the group stage matches and rank the teams within each group according to competition regulations. The match results should be determined so that the probability of a team's victory or defeat correlates with the difference in their positions on the FIBA ranking list.

### Group Stage Rules

The group stage consists of each team playing against the remaining three teams in their group. Teams receive:
- 2 points for a win,
- 1 point for a draw,
- 0 points for a loss.

Teams within a group are ranked based on the number of points. In case two teams from the same group have the same number of points, the result of their head-to-head match will be used as the ranking criterion. If three teams from the same group have the same number of points, the ranking criterion will be the point difference in their head-to-head matches (known as the "circle formation").

At the end of the group stage, the first, second, and third-placed teams from all groups are ranked from 1 to 9:
- The first-placed teams from groups A, B, and C are ranked among themselves primarily by the number of points, then by the point difference (if points are equal), and then by the number of points scored (if points and point difference are equal) to assign ranks 1, 2, and 3.
- The second-placed teams from groups A, B, and C are ranked among themselves by the same principle to assign ranks 4, 5, and 6.
- The third-placed teams from groups A, B, and C are ranked among themselves by the same principle to assign ranks 7, 8, and 9.

Teams ranked from 1 to 8 advance to the knockout stage, while the team ranked 9 does not continue in the competition.

In the output, display the results of all group stage matches by rounds, then the rankings within the groups, and which 8 teams have advanced.

### Example Output

**Group Stage - Round I:**
