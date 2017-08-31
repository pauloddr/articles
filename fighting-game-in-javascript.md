# Fighting Game in Javascript

This is a document for sharing notes and thoughts about a fighting game I am developing.

## Premises

* Full-fledged, fully featured 2.5D fighting game.
  * Hitboxes, freeze on hit, acceptable physics, cinematics, everything I can possibly make.
* Javascript: run in a modern browser, with WebGL support
  * 3D library of choice: [ThreeJS](https://threejs.org/)
* Not graphically stunning
  * This is on purpose: initially, I want to see how such a game plays in a browser
  * For the purposes of this project, Gameplay > Graphics
  * Will use "extremely low-poly" geometry as parts to assemble a humanoid "robot" -- see screenshots below
    * I'd like to improve that geometry along the run, but not as much as to impact performance
    * I'm a programmer first, and not much of an artist
  * Still, want it to look visually interesting.
    * There's the "pixel art" term for 2D graphics. Is there such a thing for 3D?
    * There are a bunch of games that are low-poly but look good.

## Graphic Concept

![Poses](http://images.pauloddr.com/articles/poses2.png)

The above image was generated in a web page, using Javascript and ThreeJS. 

So, I want to turn that into a game.

## Expected Game Modes

* Arcade Mode
* Local Versus Mode
* Campaigns
  * Story Mode
  * Character Story Mode
  * "My Story" Mode
* Creation Mode
  * Create a Character
* Offline Tournaments
  * AI Leagues
  
## Story/Environment

A year in the very far future, in a futuristic city where robots with human-like behavior live peacefully (almost) with the minority of humans that are still alive, after a change in radiation levels from the sun almost killed them all.

Each robot shares the memories of a deceased human in the form of a synthetic "brain" that is able to learn new things and make decisions, just like humans. Despite being their own "persons", robots usually have a "human trainer" that maintains and guides them.

In the game, the player him/herself takes the role of that human trainer, and the robots that populate that world are the fighters they create using the "Create a Character" feature. NPC Characters usually have NPC human trainers as well.

## Characters and Factions

12 playable characters are being planned, divided among 3 factions:

* Artists
* Enforcers 
* Rogues

Each faction has 4 characters. One character stands out from each faction, and the three together are the main protagonists of the game: one Artist, one Enforcer, and one Rogue.

Each faction has a mid-boss. They won't be playable, initially.

There will be a final boss, not belonging to any faction.

## Fighting Styles

12 distinct martial arts will be featured, one for each playable character.

Each martial art belongs to a different country, mostly related to the character's origin.

The martial arts belonging to the protagonists, and their origins, are:

* Artist - Karate (Japan)
* Enforcer - Savate (France)
* Rogue - Muay Thai (Thailand)

Other martial arts decided upon, and their origins, are:

* Artists: Kung Fu (China)
* Enforcers: Wrestling (Greece)
* Rogues: Boxing (England)

The remaining styles are still being decided or worked on.

Boss characters will feature mixed fighting styles.

## Character Customization

Players will be able to create their own characters and customize them, both visually and gameplay-wise.

Players begin creating a character by choosing a fighting style. Each fighting style has a specific, themed bonus. (Example: kung fu fighters earn a bonus to speed.)

Next, assemble the parts of the fighter/robot. Each box you see on the picture above will be able to be customized. Different geometries are expected, as well as paint jobs, accessories, lighting effects, and so on.

Then players will be able to fight, earn XP, money, and level up their characters.

Leveling up allows characters to learn skills. Skills vary from stances to attacks, defense maneuvers, movement, basically everything.

Each skill can be leveled up as well, and enhanced as the player wishes. Skills can have increased damage, stun generation, block damage, generate more SP, and so on. 

Skill frames (startup, active, recovery, hitstun, blockstun) can not be enhanced, and are always fixed. This is to avoid balance issues.

Skills are mostly related to specific martial arts, and some won't be able to be picked, for example, a wrestling skill for a kung fu fighter.

But there will be a "Free Form" fighting style that allows a character to pick skills from multiple arts. Because of that, Free Form characters don't get the bonuses they otherwise would if they picked an specific style.

## Multiplayer

This is still pretty much a research. I'm not sure it will be technically viable for a Javascript game.

But if it isn't, I'm probably going to move to a real game engine, like Unity or Unreal, to make it happen. 

But everything here is a tall order.

* Online Versus Mode
  * Ranked Match
  * Casual Match
  * Spectator Mode
  * Lobbies
    * Players can gather in a stage, hang out, and fight each other, in training or casual matches
    * Lobbies can be public or private, open or closed to spectators, etc
    * All players in the lobby, and their chosen fighters, will be on the stage at the same time
      * Think King of Fighters, when other fighters appear on the back of the stage
      * But with way more freedom and interactivity
    * There will be a fight queue that players can enter and leave at any time
      * People can just spectate forever if they want
    * While the fight happens, other players will be watching from the sides
      * They can do emotes, cheer/boo, interact with stage, or just be silly in different ways
    * After the match ends, the stage does not unload: previous fighters walk out, next fighters walk in.
      * Stage change can be done by the owner of the lobby.
    * Technical challenge: lag caused by spectators
      * Proposed solution: current players fighting can disable background players if they want, using a keyboard shortcut

## Technical Challenges

There's no control over the GC (Garbage Collector) in Javascript when running in the browser. Every time the GC runs, a "hiccup" (freeze) could be expected. Solution: avoid creating new objects during gameplay. (This will be tough.) Or, find a way to take control over GC in the browser.

Deal with different browsers and different computer setups. The bare-minimum setup is a modern browser able to run WebGL. I am thinking IE9 and above.

Multiplayer is a huge challenge in itself.

## Roadmap

### 0.1

Develop a very basic character, with one attack, and walk forward/backward. 

Test the concept of running a 3D character in Javascript and see how it performs. Does it lag or glitch in any way?

"Can we go on?"

### 0.2

Improve character with two punches, two kicks, and make hitboxes work. Add enemy character. One single hit reaction.

### 0.3

Implement crouching, and add basic crouching attacks.

### 0.4

Implement jumping, with basic aerial attacks. Add juggle hit reactions and physics.

### 0.5

Implement a "Match": health and special bars, rounds, time limit, teams.

### 0.6+

Implement the rest of the features.

## WIP

This is a work in progress.
