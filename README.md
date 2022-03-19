# Splinterlands Simulator

Simulator for battles in the [Splinterlands](https://splinterlands.com) game.

[NPM package](https://www.npmjs.com/package/splinterlands-simulator)

[GitHub](https://github.com/thechungster/splinterlands-simulator)

# Installation and Setup

To install via NPM use:

`npm install splinterlands-simulator`

A simple game can be created like so

```ts
const mylor = new GameSummoner(/* id */ 259, /* level */ 3);
const nectarQueen = new GameMonster(/* id */ 226, /* level */ 2);
const teamOne = new GameTeam(mylor, [nectarQueen]);

const tarsa = new GameSummoner(/* id */ 440, /* level */ 2);
const chicken = new GameMonster(/* id */ 131, /* level */ 1);
const forgottenOne = new GameMonster(/* id */ 404, /* level */ 1);
const teamTwo = new GameTeam(tarsa, [chicken, forgottenOne]);

const game = new Game(teamOne, teamTwo, /* shouldLog */ true);
game.playGame();

const winner = game.getWinner();
const logs = game.getBattleLogs();
```

# Configuration

The Game constructor optionally takes in **shouldLog** as a third parameter. If set to true, the game logs can be retrieved using `game.getBattleLogs()`. This returns an array of `BattleLogs`. The logs will contain the action, and the snapshot of the relevant monsters after the action has taken place.

# Samples

- [example.ts](/example.ts) for code samples.
- [Splintertools](https://splintertools.io/custom-battle) for live sample with image logs

# Simulator Accuracy

This simulator is not guaranteed to be 100% accurate and there are bugs with it. The simulator logic was based on playing the game and making educated guesses on how the simulator was working. There are still many edge cases that are probably still missing and need to be solved. If you find a bug feel free to open a PR or open an issue. If you would like to discuss the simulator you can join us on the [Splintertools discord](https://discord.com/invite/CHS3dxZmrM)

# Contributing Code

If you would like to contibute to the code base, please make pull requests to the `feature` branch. The feature branch will be merged to `master` ~once a week, and the NPM package will automatically be updated.
