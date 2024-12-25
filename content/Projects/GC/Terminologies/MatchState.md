A state is a set of variables that describe the current state of a match. 

Match state for cricket might look like this:

```javascript
const matchState = {
    innings: {
      first: {
        battingTeam: "EEE",
        totalRuns: 56,
        over: 5.5,
        wicketsFallen: 4,
        Batting: {
          striker: {
            name: "PlayerA",
            runs: 34,
            outReason: null
          },
          nonStriker: {
            name: "PlayerD",
            runs: 20,
            outReason: null
          },
          order: [
            {
              name: "PlayerX",
              runs: 0,
              status: "out",
              profileLink: "https://example.com/profile/playerx",
              outReason: ["b", "Bowler1", null]
            },
            {
              name: "PlayerY",
              runs: 10,
              status: "out",
              profileLink: "https://example.com/profile/playery",
              outReason: ["c", "Bowler2", "PlayerZ"]
            },
            {
              name: "PlayerZ",
              runs: 15,
              status: "out",
              profileLink: "https://example.com/profile/playerz",
              outReason: ["run_out", null, "PlayerX"]
            },
            {
              name: "PlayerB",
              runs: 5,
              status: "out",
              profileLink: "https://example.com/profile/playerb",
              outReason: ["st", "Bowler3", "WicketKeeperA"]
            },
            {
              name: "PlayerA",
              runs: 34,
              status: "not out",
              profileLink: "https://example.com/profile/playera",
              outReason: null
            },
            {
              name: "PlayerD",
              runs: 20,
              status: "not out",
              profileLink: "https://example.com/profile/playerd",
              outReason: null
            }
          ]
        },
        Bowling: {
	      freeHit: false,
          bowler: {
            name: "Bowler1",
            overs: 1.5,
            runsConceded: 24,
            wickets: 2
          },
          currentOver: [
            { ball: 1, runs: 4, illegal: null },
            { ball: 2, runs: 0, illegal: "no_ball" },
            { ball: 3, runs: 1, illegal: "free_hit_legal" },
            { ball: 4, runs: 0, illegal: null },
            { ball: 5, runs: 6, illegal: null },
            { ball: 6, runs: 0, illegal: null },
            { ball: 7, runs: 0, illegal: "wide" }
          ],
          order: [
            {
              name: "Bowler1",
              overs: 1.5,
              runsConceded: 15,
              wickets: 2,
              profileLink: "https://example.com/profile/bowler1"
            },
            {
              name: "Bowler2",
              overs: 2.0,
              runsConceded: 10,
              wickets: 1,
              profileLink: "https://example.com/profile/bowler2"
            },
            {
              name: "Bowler3",
              overs: 2.0,
              runsConceded: 20,
              wickets: 1,
              profileLink: "https://example.com/profile/bowler3"
            }
          ],
          extras: {
            noBalls: 1,
            wides: 2,
            byes: 0,
            legByes: 0
          }
        },
        inningsStatus: "in_progress",
        target: null
      },
      second: {
        battingTeam: "IT",
        totalRuns: 0,
        over: 0.0,
        wicketsFallen: 0,
        Batting: {
          striker: null,
          nonStriker: null,
          order: []
        },
        Bowling: {
          bowler: null,
          currentOver: [],
          extras: {
            noBalls: 0,
            wides: 0,
            byes: 0,
            legByes: 0
          }
        },
        inningsStatus: "not_started",
        target: 57
      }
    },
    interrupted: "wet_outfield",
    teamACaptain: "CaptainA",
    teamBCaptain: "CaptainB",
    teamAWicketKeeper: "WicketKeeperA",
    teamBWicketKeeper: "WicketKeeperB",
    umpires: ["Umpire1", "Umpire2"],
    matchStatus: "in_progress",
    matchoutcome: [
      null, // EEE/IT/draw/no_result
      null, // run/wickets
      null // 32/4
    ]
  };

```

