They are the constraints for the variables in [[MatchState | match state]]. They can be predefined or custom made while creating a match.

```javascript
const matchFormat = {
  totalOvers: 10,
  powerplayOvers: 2,
  legalDeliveriesPerOver: 6,

  penaltyActions: {
    noBall: () => ({
      illegal: "no_ball",
      freeHit: true,
      penalty: 1
    }),

    wide: () => ({
      illegal: "wide",
      freeHit: false,
      penalty: 1
    })
  },

  extrasActions: {
    byes: (runs) => ({
      type: "byes",
      penalty: runs,
      description: `Byes: ${runs} run(s)`
    }),

    legByes: (runs) => ({
      type: "leg_byes",
      penalty: runs,
      description: `Leg byes: ${runs} run(s)`
    })
  },

  applyPowerPlayRestrictions: (overs) => {
    return overs <= matchFormat.powerplayOvers 
      ? "Only two fielders outside the 30-yard circle during powerplay."
      : "Normal fielding restrictions apply after powerplay.";
  }
};

```
