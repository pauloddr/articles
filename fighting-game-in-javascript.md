# Fighting Game in Javascript

This is a document for sharing notes and thoughts about a fighting game I am currently developing.

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

## Graphical Concept

![Poses](http://images.pauloddr.com/articles/poses2.png)

The above image was generated in a web page, using Javascript and ThreeJS. 

So, I want to turn that into a full game.

## Roadmap

### 0.1 - Proof of Concept

Develop a very basic character, with one attack, and walk forward/backward. 

Test the concept of running a 3D character in Javascript and see how it performs. 

Does it lag or glitch in any way? Does it memory-leak? Can the leak be addressed/fixed?

"Can we go on?"

### 0.2

Improve character with two punches, two kicks, and make hitboxes work. Add enemy character. One single hit reaction.

"Is it still viable?"

### 0.3

Implement crouching, and add basic crouching attacks.

### 0.4

Implement jumping, with basic aerial attacks. Add juggle hit reactions and physics.

"How implementing physics impact the game performance?"

### 0.5

Implement a "Match": health and special bars, rounds, time limit, teams.

Publish the first public demo, make surveys, etc.

Handle feedback and reception. Improve where possible.

"Is there enough interest?"

### 0.6+

Reveal the name of the game.

Begin pre-technical-pre-PRE-alpha testing.

Implement the rest of the features.

## Story/Environment

The story of the game happens some year in the very far future, in a futuristic city where robots with human-like behavior live peacefully (almost) with the minority of humans that are still alive -- after a sudden and unexpected change in radiation levels from the sun almost killed them all.

Each robot shares the memories of a deceased human in the form of a synthetic "brain" that is able to learn new things and make decisions, just like humans. Despite being their own "persons", robots usually have a "human mentor" that maintains and guides them. Due to the large disparity between the population of robots and humans, many robots do not have human mentors, many humans mentor more than one robot, and robots may have other robots as mentors.

__In the game, the player him/herself takes the role of a human mentor of the robots they create using the "Create a Character" feature.__

NPC robots usually have NPC mentors (human or robot) as well.

## Control Scheme

One directional, and four action buttons that control the character limbs:

* Left Punch
* Right Punch
* Left Kick
* Right Kick

EX skills are performed with two punch/kick buttons at the same time.

Super skills are performed with additional directional motions.

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
  
## Characters and Factions

12 playable characters are being planned, divided among 3 factions:

* Artists
* Enforcers 
* Rogues

Each faction has 4 characters and 1 mid-boss (non-playable, initially). 

One non-boss character stands out from each faction. The three of them form the game's team of protagonists:

* one Artist (a student);
* one Enforcer (a police officer);
* and one Rogue (a cage fighter).

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

Boss characters will feature mixed/free-form fighting styles.

## Character Select Screen Disposition

<table align="center">
 <tr>
  <th>Rogues<br/>:skull:</th>
  <th>Artists<br/>:sunny:</th>
  <th>Enforcers<br/>:cop:</th>
 </tr>
 <tr>

  <td align="center">
   <br/><b>JET</b><br/><br/>

Male, Cage Fighter<br/>
Fighting Style: Muay Thai<br/>
Keywords: critical, burst
  </td>
  
  <td align="center">
   <br/><b>TERA</b><br/><br/>

Female, Student<br/>
Fighting Style: Karate<br/>
Keywords: zoner, balanced
  </td>
  
  <td align="center">
   <br/><b>PROTO</b><br/><br/>

Male, Police Officer<br/>
Fighting Style: Savate<br/>
Keywords: rushdown, combo
  </td>
  
 </tr>
 
 <tr>
 
  <td align="center">
   <br/><b>SPARKLE</b><br/><br/>

Female, Dancer<br/>
Fighting Style: ?<br/>
Keywords: ?
  </td>
  
  <td align="center">
   <br/><b>ANDROMEDA</b><br/><br/>

Male, Acolyte<br/>
Fighting Style: ?<br/>
Keywords: blind, grappler
  </td>
  
  <td align="center">
   <br/><b>CYBEL</b><br/><br/>

Female, Doctor<br/>
Fighting Style: ?<br/>
Keywords: acrobat, aerial
  </td>
 
 </tr>
 
 <tr>
 
  <td align="center">
   <br/><b>BLACKOUT</b><br/><br/>


Male, Bodyguard<br/>
Fighting Style: ?<br/>
Keywords: dirty
  </td>
  
  <td align="center">
   <br/><b>CARRION</b><br/><br/>

Female, Housewife<br/>
Fighting Style: Kung Fu<br/>
Keywords: ?

  </td>
  
  <td align="center">
   <br/><b>HAMMER</b><br/><br/>

Male, Fireman<br/>
Fighting Style: Wrestling<br/>
Keywords: grappler
  </td>
 
 </tr>
 
 <tr>
 
  <td align="center">
   <br/><b>AMP</b><br/><br/>

Female, Bounty Hunter<br/>
Fighting Style: Boxing<br/>
Keywords: rushdown, sonic
  </td>
  
  <td align="center">
   <br/><b>TICK</b><br/><br/>

Male, Merchant<br/>
Fighting Style: ?<br/>
Keywords: teleport
  </td>
  
  <td align="center">
   <br/><b>FANG *</b><br/><br/>

Female, Investigator<br/>
Fighting Style: ?<br/>
Keywords: poison
  </td>
 
 </tr>
 
</table>

`*` Probably going to change her name due to Fang being in SFV.

## Character Customization

Players will be able to create their own characters and customize them, both visually and gameplay-wise.

Players begin creating a character by choosing a fighting style. Each fighting style has a specific, themed bonus. (Example: kung fu fighters would earn a bonus to speed.)

Next, assemble the parts of the fighter/robot. Each box you see on the previous picture will be able to be customized. Different geometries are expected, as well as paint jobs, accessories, lighting effects, and so on.

Then players will be able to fight, earn XP, money, and level up their characters.

Leveling up allows characters to learn skills. Skills vary from stances to attacks, defense maneuvers, movement, basically everything.

Each skill can be leveled up as well, and enhanced as the player wishes. Skills can have increased damage, stun generation, block damage, generate more SP, and so on. 

Skill framedata (startup, active, recovery, hitstun, blockstun) are usually fixed and not able to be changed. This is to avoid balance issues.

Skills are mostly related to specific martial arts, and some won't be able to be picked, for example, a wrestling skill for a kung fu fighter. Some skills can be reused by different fighting styles (e.g., a Roundhouse Kick).

There will be a "Free Form" fighting style that allows a character to pick skills from multiple arts. Because of that, Free Form characters don't get the bonuses they otherwise would if they picked an specific style.

## Meters

* Health - HP as we know it - starts at 800 points
* Special - the blue bar for special attacks, sometimes called "Spirit" - starts at 100 points
* Shield - defense system - starts at 400 points
* Focus - stun system - starts at 400 points

There won't be a "guard break" mechanic upon Shield depletion, but rather, attacks will begin causing damage on block -- even normal ones -- and some defensive features (like pushblock) will be disabled.

Focus depletion causes the character to be stunned. Its amount can be increased, and the time the character remains stunned can be decreased by attributes.

## Attributes

Enhanced by leveling up. Each attribute will have a max of 50 points.

The max level of a character will be 100, and each level gives one attribute point to use.

* Strength - enhances melee damage to Health and Shields, and throw damage to Health.
  * This makes your melee and throw attacks stronger overall.
  * Throws do not cause Shield damage.
* Vitality - enhances Health points, Shield points, and Focus points.
  * This increases your overall survivability.
* Agility - enhances movement speed, and Shield/Focus recovery speed.
  * This makes you move faster, even out of danger, so you can recover faster.
* Dexterity - enhances melee, throws, and projectile damage to Focus.
  * Causes your attacks to hit more accurately, stunning your enemies faster.
* Intelligence - enhances Special points gained by using skills, and projectile damage to Health and Shields.
  * Enhances your "spirit", causing your projectiles to be stronger.
  * You also execute your skills more intelligently and efficiently, yielding more benefits in the form of additional Special points earned.
* Charisma - reduces the time Focus and Shield begin recovering after you stop receiving attacks, and reduces stun duration.
  * You are loved! The support of your fans brings you to your feet faster! :)

Along with Custom Characters, Canon and NPC Characters will also have their builds based on this system.

Each point increases the mentioned attributes by 1% each. So Vitality enhances HP by 50% when 50 points are invested, making it reach 1200 points.

It's a linear system, without diminishing returns on the base value. That way, players won't feel "forced" to balance out their attributes just because investing in a single node is less effective. If players want to invest everything in Strength and Vitality, so be it, but they will move and recover slower, cause less stun, have weak SP generation, etc.

It also brings offense and defense more in line: a character with max offense will take out a character with max defense in the same time it would take if both of them had no bonuses at all. No attributes "multiply" around each other: that's why I don't plan on implementing a mechanic for "damage resistance", for example, because it multiplies around Health points, thus causing potential balance issues.
     
## AI Leagues

The AI (Artificial Intelligence) in this game will be used for all CPU-controlled robots and also have its own mode.

Developing an AI involves creating a tree of decisions the robot will make based on a number of criteria.

A full game mode, called __AI Leagues__, will be available for players to take advantage of building the most perfect AIs possible.

The robots are purely controlled by the AI built by the player. The player won't be able to control the robots in this mode.

Players will take their robots to championships (Leagues) where each robot in the league fights other players' robots (or NPCs, if not enough players register). Each participant fights each other in a League at least once.

Rankings will be based on W/L ratio (both of matches and rounds), with total damage dealt being used as tie breaker.

Those Leagues are run ONLINE (in other words: on a server), with the replays being available for the player and general public to watch. All fights will run on a schedule, and they will be able to be watched as they happen -- leaderboards being updated in real time as well.

League Tiers:

* Local Leagues - player goes to an specific gym in the city and registers their characters in their leagues. Those are run daily.
* District Leagues - player registers their characters on district leagues that are run weekly.
* Regional Leagues - players registers their characters on city leagues that are run bi-weekly.
* Major Leagues - player registers their characters on country-wide leagues that are run monthly.
* Global Leagues - player registers their characters on worldwide leagues that are run over the course of three months.

Characters will need to unlock the next tiers by placing above certain ranks in the leaderboard. Once a character unlocks the next tier, it (usually) can not return to the previous tier. So characters that are dominating in Local Leagues, once they get "promoted" to the next tier, they can no longer play Locals. This makes Local Leagues more of an entry point, and gives everyone a fair chance. Rewards will be balanced around this, so playing on District Leagues (which take longer) yields similar rewards as running Local Leagues seven times (and so on). In practice, this will be reflected on the number of contestants allowed in those Tiers, as the more they fight, the more rewards they earn.

Entering a League costs a fee of in-game credits.

Rewards for all League Tiers:

* League XP - participating in a League gives that character "League XP" which can be used to improve their AI skills. All characters earn the same amount of XP, regardless of placement.
* Normal XP - characters will earn a reduced amount of normal XP in this mode.
* Credits - the better the placement, the more credits are awarded. Depending on placement, players will earn back what they paid to enter the League. If character keeps performing poorly, player will end up losing credits.
* Unique rewards are being considered for the best contenders, such as gear, titles, etc.

Some rewards are immediately earned as soon as a participant finishes a round (win or lose) in the League. The player will be able to improve/change the character over the course of a League. Additional rewards (related to placement) will be earned after all fights are finished.

AI Skills are mirrored after abilities necessary for people to succeed in fighting games:

* __Execution__: how fast skill inputs are entered, and without mistakes
  * Robots will also "input directional and button presses" just like players would do
  * A low execution skill will make the robot miss commands and combos
* __Reaction__: how fast robots react to skills used against them
  * Robots will "memorize" skills the more they're used against them
  * Low reaction skills will make the robots make a decision too late, or a bad one
* __Confirms__: how precisely the robot can follow up after a skill hit/blocked/whiffed
  * A "hit confirm" allows the robot to hit another skill in succession after the enemy has been hit
    * And also *not* to follow up with another skill if the first hit was blocked, preventing punishment
  * A "blocked confirm" will make the robot follow up with another skill after the enemy blocked the first hit
    * This will usually make the attacking robot vulnerable to punishment
  * A "blank confirm" will make the robot follow up with another skill *anyway*. This is a grey area which may have positive or negative consequences for the robot performing the attacks.
    * This is like executing an skill after another that may or may not hit the enemy because they're moving, jumping, etc.
  * Having high confirm skills allows the "hit confirm" chance to be higher, diminishing the other two chances.

AI Skills can not be enhanced in a way that they're always successful. There will always be a small chance for AI Skills to fail.

Other fighting game skills such as "Meaties" (making skills hit at the last possible active frame), Conditioning (making the enemy perform something based on a pattern) and "the Shimmy" (walking away from close range after conditioning the enemy to throw) can be simulated by building the behaviors and decisions of the robot in the normal AI building process.

## Multiplayer

This is the Online Versus mode as we know it, with characters controlled by players.

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

There's no control over the GC (Garbage Collector) in Javascript when running in the browser. Every time the GC runs, a "hiccup" (freeze) could be expected, depending on how many objects are made available for the GC to free. Solution: avoid creating new objects during gameplay. (This will be tough.)

Deal with different browsers and different computer setups. The bare-minimum setup is a modern browser able to run WebGL. I am thinking IE9 and above.

Multiplayer is a huge challenge all in itself.

## Monetization

As I intend to work on games for a living, by all means I plan on monetizing this game, if technical challenges are resolved.

### Trial Version

The Trial Version is intended to give players a basic notion of how the game plays.

* No account registration required.
* Tera as a free playable character.
* Only one mode available: Versus CPU.
* Can adjust controls and some game options.

Any purchases will require the player to register for an account.

### Coin System (Gold/Silver)

Registering for an account allows the player to purchase Gold coins (with real money), which are then used to make purchases in store.

There will be ways to earn free Gold coins, such as answering surveys, advertising the game, and so on.

Silver coins will be able to be earned through normal gameplay. Some items in the store will be purchasable with Silver coins.

Silver coins cannot be converted to Gold coins.

### Ads

The game may display external ads if no purchases are made. Players are free to block them if they want.

Registering for an account, then making the first purchase of Gold coins, will remove ads forever.

Earning free Gold coins (and not making any purchases) will not remove ads.

### Full Base Game

The full base game is a discounted package that includes the following:

* 12 characters
* 12 fighting styles
* 14 stages
* All model parts from unlocked characters
* Modes: Arcade, Story, Versus, Training, AI Leagues
* 12 Character Creation slots
* 4 Costume Slots for each custom Character
* Free-form fighting style.

### Microtransactions

If players do not want to purchase the full base game, they can purchase features separately.

* Registering for an account unlocks for free: Arcade Mode, Versus Mode (vs. Local Player), and Training Mode.
  * Tera remains a free character after registration.
* Story Modes are sold separately.
* Characters, fighting styles, model parts, and stages can all be purchased separately.
* Free-form fighting style:
  * It only unlocks the _ability_ of using different skills from different fighting styles.
  * The player still needs to purchase other fighting styles to make them available in Free-form.
  * Free-form will cost the same as a single fighting style.
* Character Creation is purchasable through Character Slots.
  * Buying the first slot unlocks AI Leagues Mode.
  * Each Custom Character has 2 Costume Slots available.
  * More Costume Slots can be purchased separately, and they are account wide.
  
__Bundles__ are packages with multiple features for a discounted price.

* Character Bundle: a single character, including the fighting style, stage, character story, and all model parts belonging to that character, as well as a Character Slot.
* Fighting Style Bundle: a single fighting style (Free-form included), with an additional Character Slot.

### DLC

Potential DLCs include:

* More model parts or sets
* Exotic fighting styles (e.g., Sport-themed arts)

### Season Passes?

Still not decided about this. I tend to like the idea of Expansion Packs instead of Season Passes. They seem like the same thing, but for some reason people tend to dislike the latter. Semantics...

### Refund Policy

Purchases of Gold coins (with real money) aren't refundable (usually).

If players purchase anything that is part of a Bundle, then later decide to buy the Bundle itself, the previous transaction will be undone and refunded (as Gold/Silver coins, depending on what was used). This also applies to the full base game purchase.

Additionally, if the player is not happy with a purchase, they can return it within 3 days of the purchase. This only applies to the first purchase of said feature though. If the player purchases the same feature a second time, it won't be able to be refunded this way.

Full (real money) refunds can be considered if the player isn't happy at all with the game and wants to close their account within a certain time after it has been created.

## News and Updates

I usually report my progress on [Twitter](https://twitter.com/paulo_ddr).

## WIP

As this is a Work In Progress, all information is subject to change.
