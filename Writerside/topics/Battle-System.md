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

# Failure Conditions
In the case a Player loses their HP, they are reset to the most recent Checkpoint.