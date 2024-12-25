A **match event** is an atomic change or action that alters the state of a match. In this case, the event will represent a change. It is a subset of [[MatchState|Match State]].

The event size should be as minimal as possible. It should contain _just enough_ information to convey every change in the state. Avoid specifying information that can be derived. (for example, in the examples timestamp and penalty can be calculated in the server itself without having to be passed explicitly)

An event for runs scored might look like:

```javascript
const event24 = {
  type: "run_scored", 
  details: {
    runs: 4,
    scoringType: "boundary", // "run", "byes", "legbyes", "dot"
    illegal: "no_ball", // "wide"
    penalty: 1, // 0 for legal
  },
  timestamp: new Date()
};

```

An event for wicket fallen might look like:

```javascript
const event24 = {
  type: "wicket_fallen", 
  details: {
    playerOut: "PlayerX", // needed for case like runouts, munkading etc
    outReason: ["b", "Bowler1", null],
    illegal: null,
    penalty: null 
  },
  timestamp: new Date()
};

```