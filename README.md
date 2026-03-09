# LaLiga API

This project is an ASP.NET Core Web API that simulates a football league system. It allows users to manage teams, matches, and automatically generate league standings.

## Features

The API includes the following functionality:
### Teams
- Create teams
- Get all teams
- Get team by ID
- Update team
- Delete team

### Matches
- Create matches
- Get all matches
- Get match by ID
- Update match
- Delete match

### Standings
- Generate league table dynamically from match results
- Get full standings
- Get standings for a specific team

## Technologies Used
- ASP.NET Core Web API
- Entity Framework Core
- SQL Server
- RESTful API design

## Unique Design Decisions
### Team Acronyms as Primary Keys
Instead of using numeric IDs, teams use their acronym as the primary key and macthes use the combination of these names for their primary key.
Example:RMA - Real Madrid
BAR - Barcelona
ATM - Atletico Madrid
Example match:
HomeTeam: RMA
AwayTeam: BAR
Match: RMABAR

### Dynamic League Table
The standings table is not stored permanently in the database.
Instead, it is **calculated dynamically** using match results:
Statistics calculated include:
- Matches Played
- Wins
- Draws
- Losses
- Goals For
- Goals Against
- Goal Difference
- Points

Points are calculated using the standard football rule:
Win = 3 points
Draw = 1 point
Loss = 0 points

## API Endpoints
### Teams
GET /api/teams
GET /api/teams/{id}
POST /api/teams
PUT /api/teams/{id}
DELETE /api/teams/{id}

### Matches
GET /api/matches
GET /api/matches/{id}
POST /api/matches
PUT /api/matches/{id}
DELETE /api/matches/{id}

### Standings
GET /api/standings
GET /api/standings/{teamId}


## How to Run the Project
1. Clone the repository
2. Open the project in Visual Studio
3. Configure the database connection
4. Run the project
5. Test endpoints using Swagger.

## Author
Project developed as part of a backend API exercise to showcase .NET knowledge depth.
