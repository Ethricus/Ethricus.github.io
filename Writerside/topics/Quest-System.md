# Quest System

## data structures
To make it easier to integrate the quest system with the main menu, it would be good if the quest systems data, at least for the base data about the quests could be stored in a scriptable object.

Proposed structure:
- Int quest ID
- String quest name
- String quest description
- string quest steps[]

More can be added to this as needed but ideally at least these should be stored. This will also allow for the save file to save the quest ID and which step it is on to track where the player is in the game easily. 