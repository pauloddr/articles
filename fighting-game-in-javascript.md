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

## Expected Game Modes

* Arcade Mode
* Versus Modes
  * Versus Local Player
  * Versus CPU
* Campaigns
  * Story Mode
  * Character Story Mode
  * "My Story" Mode
* Creation Mode
  * Create a Character
  * AI Leagues

## Control Scheme

The standard directional + four action buttons scheme:

* Light Punch
* Heavy Punch
* Light Kick
* Heavy Kick

Powered-up command skills are performed with two punch/kick buttons at the same time.

Super skills are performed with additional directional motions.

## Meters

* Health - HP as we know it - starts at 800 points
* Special - the blue bar for special attacks, sometimes called "Spirit" - starts at 100 points
* Shield - defense system - starts at 400 points
* Focus - stun system - starts at 400 points

There won't be a "guard break" mechanic upon Shield depletion, but rather, attacks will begin causing damage on block -- even normal ones -- and some defensive features (like pushblock) will be disabled.

Focus depletion causes the character to be stunned. Its amount can be increased, and the time the character remains stunned can be decreased by attributes.

The "comeback mechanic" will be called _Guardian Drive_. It has its own gauge, filled as the character takes damage, performs certain moves, or (for custom characters) builds their character in a certain way.

## Story/Environment

The story of the game happens some year in the very far future, in a futuristic city where robots with human-like behavior live peacefully (almost) with the minority of humans that are still alive -- after a sudden and unexpected change in radiation levels from the sun almost killed them all.

Each robot shares the memories of a deceased human in the form of a synthetic "brain" that is able to learn new things and make decisions, just like humans. Despite being their own "persons", robots usually have a "human mentor" that maintains and guides them.

__In the game, the player him/herself takes the role of a human mentor of the robots they create using the "Create a Character" feature.__

## Characters, Factions, and Fighting Styles

Initially, the game will feature 12 playable characters. Those are the NPCs (Non-Player Characters).

Each NPC knows a different fighting style, each from a distinct country of origin. A few styles are listed below:

* Karate
* Savate
* Muay Thai
* Kung Fu
* Wrestling
* Boxing

Characters in general (NPCs and PCs) can be divided among 3 factions:

* Artists
* Enforcers 
* Rogues

Each faction has four NPCs and one mid-boss (non-playable, initially). There will be a final boss, not belonging to any faction. All bosses will feature a "Free Form" fighting style.

## Character Select Screen Disposition

Here is a preview list of the 12 playable characters, their factions, ocupations, and fighting styles.

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
Keywords: burst
  </td>
  
  <td align="center">
   <br/><b>TERA</b><br/><br/>

Female, Student<br/>
Fighting Style: Karate<br/>
Keywords: zoner
  </td>
  
  <td align="center">
   <br/><b>PROTO</b><br/><br/>

Male, Police Officer<br/>
Fighting Style: Savate<br/>
Keywords: combo
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
Keywords: blind
  </td>
  
  <td align="center">
   <br/><b>CYBEL</b><br/><br/>

Female, Doctor<br/>
Fighting Style: ?<br/>
Keywords: acrobat
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
Keywords: rushdown
  </td>
  
  <td align="center">
   <br/><b>TICK</b><br/><br/>

Male, Merchant<br/>
Fighting Style: ?<br/>
Keywords: teleport
  </td>
  
  <td align="center">
   <br/><b>TALON</b><br/><br/>

Female, Investigator<br/>
Fighting Style: ?<br/>
Keywords: poison
  </td>
 
 </tr>
 
</table>

## Character Customization

Aside from playing NPCs, players will also be able to create their own characters and customize them, both visually and gameplay-wise.

Players begin creating a character by choosing a fighting style. Each fighting style has a specific, themed bonus. (Example: kung fu fighters would earn bonuses to speed.)

Next, assemble the parts of the fighter/robot. Each box you see on the previous picture will be able to be customized. Different geometries are expected, as well as paint jobs, accessories, lighting effects, and so on.

Then players will be able to fight, earn XP, money, and level up their characters.

Leveling up allows characters to learn skills. Skills vary from stances to attacks, defense maneuvers, movement, basically everything.

Each skill can be assigned input sequences (and some have small advantages, like charge motions) and leveled up as well, and enhanced as the player wishes. Skills can have increased damage, stun generation, block damage, generate more SP, and so on. 

Skill framedata (startup, active, recovery, hitstun, blockstun) are usually fixed and not able to be changed. This is to avoid balance issues.

Skills are mostly related to specific martial arts, and some won't be able to be picked, for example, a wrestling skill for a kung fu fighter. Some skills can be reused by different fighting styles (e.g., a Roundhouse Kick).

There will be a "Free Form" fighting style that allows a character to pick skills from multiple arts. Because of that, Free Form characters don't get the bonuses they otherwise would if they picked an specific style.

## Attributes System

The Attributes System is shared by NPCs and PCs alike.

They are enhanced by the character level. Each attribute will have a max of 50 points.

The max level of a character will be 100, and each level gives one attribute point to use.

* __Strength__ - enhances melee damage to Health and Shields, and throw damage to Health.
  * This makes the character's melee and throw attacks stronger overall.
  * Throws do not cause Shield damage.
* __Vitality__ - enhances Health points, Shield points, and Focus points.
  * This increases the character's overall survivability.
* __Agility__ - enhances movement speed, and Shield/Focus recovery speed.
  * This makes the character move faster, even out of danger, so they can recover faster.
* __Dexterity__ - enhances melee, throws, and projectile damage to Focus.
  * Causes the character's attacks to hit more accurately, stunning their enemies faster.
* __Intelligence__ - enhances Special points gained by using skills, and projectile damage to Health and Shields.
  * Enhances the character's "spirit", causing their projectiles to be stronger.
  * The character also executes their skills more intelligently and efficiently, yielding more benefits in the form of additional Special Points earned.
* __Charisma__ - reduces the time Focus and Shield begin recovering after you stop receiving attacks, and reduces stun duration.
  * The character is loved! The support of their fans brings them to their feet faster! :)

Each point increases the aforementioned attributes by 1% each. So Vitality enhances HP by 50% when 50 points are invested, allowing it to reach 1200 points.

It's deliberately a linear system, without diminishing returns on the base value. That way, players won't feel "forced" to balance out their attributes just because investing in a single node would be less effective. If players want to invest everything in Strength and Vitality, so be it, but they will move and recover slower, cause less stun, have weak SP generation, etc.

It also brings offense and defense more in line: a character with max offense will take out a character with max defense in the same time it would take if both of them had no bonuses at all.

Attributes that "multiply" around each other tend to bring unbalance, so they will be used sparingly (if at all). Example: a "damage resistance" mechanic, which multiplies around maximum Health Points.

## AI Modes

The AI (Artificial Intelligence) in this game will be used for all CPU-controlled robots and also have its own mode.

Developing an AI involves creating a tree of decisions the robot will make during a fight, based on a number of criteria.

AI building will be made available for players to take advantage of creating the most perfect AIs possible.

__In this mode, the robots will be purely controlled by the AI built by the player__. The player has no control of the robots, other than creating an "AI build" for them.

Players will then take their robots to Championships, where each robot in the league fights other players' robots (or NPCs, if not enough players register). 

In a League, each participant fights each other at least once.

Rankings will be based on W/L ratio (both of matches and rounds), with a mix of total damage dealt and taken being used as tie breaker.

Those Leagues are run ONLINE (in other words: on a server), with the replays being available for the player and general public to watch. All fights will run on a schedule, and they will be able to be watched as they happen -- leaderboards being updated in real time as well.

League Tiers:

|Tier|Length|Description|
|---|---|---|
|Local Leagues|1 day|Run by local gyms, several of them across the city.|
|District Leagues|1 week|Run by each of the four districts in the game.|
|Regional Leagues|2 weeks|Decides the best among all districts.|
|Major Leagues|1 month|City versus city.|
|World Leagues|3 months|Only the best will get this far.|

Characters will need to unlock the next tiers by placing above certain ranks in the leaderboard. Once a character unlocks the next tier, it (usually) can not return to the previous tier. So characters that are dominating in Local Leagues, once they get "promoted" to the next tier, they can no longer play Locals. This makes Local Leagues more of an entry point, and gives everyone a fair chance. Rewards will be balanced around this, so playing on District Leagues (which take longer) yields similar rewards as running Local Leagues seven times (and so on). In practice, this will be reflected on the number of contestants allowed in those Tiers, as the more they fight, the more rewards they earn.

Rewards for all League Tiers:

* __AI XP__ - participating in a League gives that character "AI XP" which can be used to improve their AI attributes. All characters will earn the same amount of AI XP, regardless of placement.
* __Normal XP__ - characters will earn a reduced amount of normal XP in this mode.
* __Credits__ - Entering a League costs a fee of in-game credits. The higher the League Tier, the more expensive the fee will be. The better the placement, the more credits will be awarded. Depending on placement, players will earn back what they paid to enter the League, and the top contenders will get a bonus. If character keeps performing poorly, player will end up losing credits.
* Unique rewards can be considered for the best characters, such as gear, titles, etc.

Some rewards are immediately earned as soon as a participant finishes a round (win or lose) in the League. The player will be able to improve/change the character over the course of a League. Additional rewards (related to placement) will be earned after all fights are finished.

__AI attributes__ are mirrored after attributes necessary for people in general to succeed in fighting games:

* __Execution__: how fast skill inputs are entered, and without mistakes.
  * Robots will not "execute skills directly", but rather "input directional and button presses" just like players would do.
  * A low execution skill will make the robot miss commands and combos, or with messed-up timing.
* __Reaction__: how robots react to skills used against them in a way that the enemy ends up punished.
  * Robots will "memorize" skills the more they're used against them (see __Memory__ attribute).
  * Low reaction skills will make the robots make a decision too late, or a bad one.
  * Tech throwing, for example, falls under this category.
* __Confirms__: how precisely the robot follows up after a skill connects (or not).
  * A "hit confirm" allows the robot to hit another skill in succession after the enemy has been successfully hit.
    * This is the essence of hit-confirms.
    * Low execution skill may mess the timing of the follow-up skill and allow the enemy to block/counter.
  * A "missed confirm" happens when the robot successfully hits with a skill, but does not execute the follow up.
    * This will be a missed opportunity, but not yield negative results to the attacker.
    * Wrong execution (caused by low execution skill) that prevents the follow-up skill to execute does not count as a "missed confirm".
  * A "blocked confirm" will make the robot follow up with another skill after the enemy blocked the first hit.
    * This will usually make the attacking robot vulnerable to punishment.
  * A "blank confirm" will make the robot execute the first and follow-up skills "in thin air".
    * This is a grey area which may have positive or negative consequences for the robot performing the attacks.
    * This is like executing an skill after another that may or may not hit the enemy because they're moving a lot, jumping around, etc -- like "fishing" for a hit.
  * Having high confirm skills allows the "hit confirm" chance to be higher, decreasing the other chances.
* __Memory__: increases the amount of skills that can be remembered by the robot, and for how long.
  * When a skill is using against the robot, that skill goes into the robot's "memory", allowing the robot to react to that skill in a specific way (decided by the player).
  * Other skills will be used and be memorized in the same way.
  * The more the same skill is used against the robot, the longer it will take for that skill to be forgotten.
  * Skills that are less used against the robot will be "discarded" by other, more rememberable skills.
  * Increasing this skill makes the robot remember more skills, and keep them longer.
* __Actions__: increases the amount of different actions that can be performed by the robot.
  * This is the essence of AI building.
  * An "action" is something like, "approach", "jump back", and so on.
  * Actions can have conditions associated to them, and they can be ordered by priority.
  * More actions create more situations for your robot to succeed.
  * There are a number of inherited actions that do not take action slots and are always available, such as "block" and "attack randomly".
* __Combos__: build a combo tree for your robot.
  * Multiple branches are allowed, and they can have conditions attached to them.
    * Example: `[LK]` -> `[HK]` or a `[Super]` (if enough SP is available).
  * Next hits in a combo are dependent on __Confirms__ attribute.
    * Example: `[LK]` -> `[HK]`: if `[LK]` hits before `[HK]` is executed, a "confirm check" is performed. If it rolls a "Hit Confirm" (good outcome) or "Blocked Confirm" (bad outcome), `[HK]` will execute.
  * It is possible to use special combo skill `[Force Next]` to always execute the next move, regardless of the __Confirms__ attribute. But this has an additional cost - see next item.
    * A "pressure combo": `[LK]` -> `[Force Next]` -> `[Special]` (a safe one)
  * Each skill added to the combo tree takes an amount of points to use.
    * Normals: 1 point.
    * Specials: 3 points.
    * Supers: 5 points.
    * Force Next: 1 point.

Each AI attribute will have a maximum of 50 points, and the maximum AI level is 100 - just like normal level progression and attributes.

AI attributes can not be enhanced in a way that they're always successful. There will always be a chance for them to fail. Below is the list of effects for each attribute when they're maxed out at 50 points:

* __Execution__: 90% input accuracy and precise timing while entering skill inputs.
* __Reaction__: make a decision 5x faster (compared to zero points).
* __Confirms__: increases "Hit Confirm" chance up to 85%, leaving the others (Missed Confirm, Blocked Confirm, Blank Confirm) at 5% each.
* __Memory__: each point increases the "memorized skill slot" count by +1, and increases the amount of time it takes for a skill to be forgotten by 2%. Robots begin with 5 memory slots.
* __Action__: each point gives one additional action slot. Robots begin with 5 action slots.
* __Combos__: each point gives one additional combo point. Robots begin with 5 combo points.

Other fighting game skills such as "Meaties" (making skills hit at the last possible active frame), "Conditioning" (making the enemy perform something based on a pattern) and "the Shimmy" (walking away from close range after conditioning the enemy to throw) can be simulated by building the behaviors and decisions of the robot in the normal AI building process.

## Multiplayer

This is the Online Versus mode as the FGC knows it, with characters being controlled by players.

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

As I intend to work on games for a living, I most definitely plan on monetizing this game, if technical challenges are resolved -- and there is enough interest.

### Trial Version

The Trial Version is intended to give players a basic notion of how the game plays.

* No account registration required.
* Tera as a free playable character.
* Only one mode available: Versus CPU.
* Can adjust controls and some game options.

Any purchases will require the player to register for an account.

### Full Base Game

The full base game will include the following:

* 12 Characters
* 12 Fighting Styles + Free Form
* 14 Stages
* All model parts from unlocked characters
* Modes: Arcade, Story, Versus, Training, Character Creation, AI Leagues
* 13 Character Slots (one for each Fighting style + Free Form)
* 4 Costume Slots for each custom Character

### Microtransactions

If players do not want to purchase the full base game, they can purchase features separately.

* Registering for an account unlocks for free: Arcade Mode, Versus Mode (vs. Local Player), and Training Mode.
* After registration, unlock one of the following characters for free: __Tera__, __Proto__, or __Jet__.
  * This does not unlock anything else, just the characters.
* Story Modes are sold separately.
* Characters, fighting styles, model parts, and stages can all be purchased separately.
* Free-form fighting style:
  * It basically unlocks the _ability_ of using different skills from different fighting styles.
  * The player still needs to purchase other fighting styles to make them available in Free-form.
  * Free-form will cost the same as a single fighting style.
* Character Creation is purchasable through Character Slots.
  * Buying the first slot unlocks AI Leagues Mode.
  * Each Custom Character has 2 Costume Slots available.
  * More Costume Slots can be purchased separately, and they are account wide.
  
__Bundles__ are packages with multiple features for a discounted price.

* Character Bundle: a single character, including the fighting style, stage, character story, and all model parts belonging to that character, as well as a Character Slot.
* Fighting Style Bundle: a single fighting style (Free-form included), with an additional Character Slot.

### Coin System (Gold/Silver)

Registering for an account allows the player to purchase Gold coins (with real money), which are then used to make purchases in store.

There will be ways to earn free Gold coins, such as answering surveys, advertising the game, and so on.

Silver coins will be able to be earned through normal gameplay. Some items in the store will be purchasable with Silver coins.

Silver coins cannot be converted to Gold coins.

### Ads

The game may display external ads if no purchases with real money are made.

Registering for an account, then making the first purchase of Gold coins, will remove ads forever.

Earning free Gold coins (and not making any purchases) will not remove ads.

Players are free to block ads if they want, and the game won't bother them if they're using ad blockers.

### DLC

Potential DLCs include:

* More model parts or sets
* Exotic fighting styles (e.g., Sport-themed arts)

### Season Passes?

Still not decided about this. I tend to like the idea of Expansion Packs instead of Season Passes. They seem like the same thing, but for some reason people tend to dislike the latter. Semantics...

### Refund Policy

Purchases of Gold coins (with real money) aren't refundable (usually).

If players purchase anything that is part of a Bundle, then later decide to buy the Bundle itself, the previous transaction will be undone and refunded (as Gold/Silver coins, depending on what was used). This also applies to the full base game purchase.

The free character unlocked upon registering for an account counts as a Silver coins transaction. If the player later purchases a Bundle containing the chosen character, that amount of Silver coins will be given to the player.

Additionally, if the player is not happy with a purchase, they can return it within 7 days of the purchase. This only applies to the first purchase of said feature though. If the player purchases the same feature a second time, it won't be able to be refunded this way.

Full (real money) refunds can be considered if the player isn't happy at all with the game and wants to close their account after a certain time it has been created.

## News and Updates

I usually report my progress on [Twitter](https://twitter.com/paulo_ddr).

## WIP

As this is a Work In Progress, all information is subject to change.
