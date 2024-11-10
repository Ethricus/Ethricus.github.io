# Git

# Branching Structure
Branches all perform a different function in the project for organization purposes.
There is an order that branches are pushed to ensure they work correctly before being integrated into the main project.

| Branch name | Purpose | merge into | pull from |
| ----------- | ------- | ---------- | --------- |
| master | The latest releasable version of the project once a release has been finalised | N/A | releases/ |
| hotfixes/ | Hotfixes for the latest release if critical bug(s) are discovered after release | master & develop | master |
| releases/ | The current planned release for the public | master | develop |
| develop | A branch that holds all work completed to date, pulling from both branches hierarchically above and below | releases/ | master |
| patches/ | Where features or otherwise are merged together where they are interconnected, or would cause conflicts. | develop | features/ & develop |  
| features/ | Brand-new features being developed | develop | develop |
| bugs/ | Bug fixes | develop | branch containing the bug |
| misc/ | Miscellaneous branches that do not directly fall under any other category. | develop | develop | 