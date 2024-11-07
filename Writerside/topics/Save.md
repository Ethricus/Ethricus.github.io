# Save

# save
When the game is saved it needs to save all of the information held by the DDOL systems which are used to track progression, it also needs to hold player data.

DDOL is used to hold persistent data. All objects in the game that needs to be saved between sessions need to be reading and writing data to DDOL. Each DDOL system will then save and reload it's data when the player selects to save.

A suggestion for data saving is using JSON which is supported by unity and used extensively. However this makes the files readable and editable to the player which could cause cheating issues. As the game isn't online or multiplayer this may be less of an issue as it's an issue of how the player wishes to play the game. 
