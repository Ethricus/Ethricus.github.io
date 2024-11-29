# Battle System

## Statistics 
- **Level** - The Level the character is at. This affects the base stats of a character according to a modifier set by the Level. (max 100)
- **HP** - How much health a character has, in base stats this defines Max HP. (max 10000)
- **SP** - Seri Points define a limit on how much Seri a character can use, each Seri attack uses a different amount of SP. (max 100)
  SP can be recovered through physical attacks or resting.
- **EXP** - Experience - TBD
- **P. ATK** - Physical Attack affects how much damage melee attacks do, this value is affected by the equipped weapon's stats. (max 200)
- **P. DEF** - Physical Defense affects how much damage is taken from a melee attack. (max 200)
- **S. ATK** - Seri Attack affects how much damage Seri attacks do, this value is affected by the equipped weapon's stats. (max 200)
- **S. DEF** - Seri Defense affects how much damage is taken from Seri attacks. (max 200)
- **Agility** - Agility affects speed and response time in order to parry attacks.
- **Luck** - Luck affects the chance for a Critical Attack.

## Battle Equations
![9d86c93c-e99c-41e1-88ee-9d8191c885b5.png](9d86c93c-e99c-41e1-88ee-9d8191c885b5.png)
![5236a9d0-66ea-49c8-b41e-72ef71174518.png](5236a9d0-66ea-49c8-b41e-72ef71174518.png)
![4b286c87-7192-47b3-a1ff-c915f606f229.png](4b286c87-7192-47b3-a1ff-c915f606f229.png)

## Character Leveling
The player can level up by gaining EXP, each Level has a different EXP threshold; the higher your level is, the more EXP is required.

Ways to obtain EXP:
- Completing Quests - Completing Quests will reward the player with EXP.
- Fighting Enemies - Fighting enemies rewards EXP; how much is rewarded is dependent on the enemy's relative level as well as the difficult chosen.

## Weapons and Weapon Leveling
Weapons have two modifiers - P.ATK and M.ATK. Leveling weapons can increase these modifiers.

Leveling up a weapon requires both Money and Materials. The amount of each required depends on the weapon itself as well as the amount modified.

## Failure Conditions
In the case a Player loses their HP, they are reset to the most recent Checkpoint.

## rewrite 
the battle system is currently undergoing a massive rewrite as part of the development for the inventory system. Proposed changes will be details below 

## Classes 
* **Battle Manager** - a singleton which handles calculations for attacks rather than each battle script. The battle information script will pass over a reference to itself and the attack info struct when an attack collides, this will then calculate how this effects stats and send it back to the player/enemy or change the stats itself (which it will do is currently in question due to class access issues) 
* **Battle Stats** - rewrite of the BattleInfo class 
* **Attack Classes** - individual attacks will have implementations that will be modified in value by the stats of the gameobject that creates the 
* **Attack List** - List of attack gameobjects with an ID which can then be used to fix and match what attacks enemies can use or for the player to gain new attack types. attack lists will likely be implemented on a class specific basis rather than being one list like inventory is. 
* **Accessory classes** - need a way to be added to the Battle stat script with an add and remove function. when added they are removed from inventory and when removed they are added back. 
* **Weapon Classes* - need a more complex class than accessories, can add, remove and also has implementations for equipping it. weapons have info in them for attack modifiers specifically which are calculated without being added to the players base stats, though can also affect base stats. only one weapon can be equipped at a time, they do not get removed from the inventory list while in use but show as in use in UI. 
* **Attack Collider** - a collider which deals damage and passes attack data when collider with, mirror of what I tried to do in my FYP rewrite. used on attack seperate to the Gameobject but also as a way to turn on and off physical attack damage when an attack is active or not. (e.g. if not attacking, touching the players sword should not cause damage to an enemy)  

