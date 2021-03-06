# Bombhellman
2D Game Bomberman-like, C/SDL

Code can be used as boilerplate for 2D games C/SDL : classic structures, game loop...etc

Game: minimum features
-------------------
- Managing mouvements
- Managing worlds
- Bombs
- Modifiers / Life
- Monsters
- Pause
- Save & Load Game
+ Other features are implemented as well

Play:
----
- Choose new game from the main menu, and start playing!

Compiling & Setup:
-----------------
- Dependencies : 
* gcc, SDL library (beware : v1.2), SDL_Image library (v1.2), SDL_Mixer (v1.2)
* e.g on Debian based distributions:
  sudo apt-get install build-essential libsdl1.2-dev libsdl-image1.2-dev libsdl-mixer1.2-dev

- Then from the project main directory: make
  (Binary will be located in bin/)

- Run binary from project main directory: bin/bombeirb
(other sprites and some components won't be loaded otherwise e.i relative path)

Default Controls:
----------------
- Arrow keys (up,down,left,right) : mouvements, menu choose buttons
- Return : choose an option in the menu
- Space : set a bomb
- p : pause
- s : save

Notes:
-----
- When saving one profile is available: "default"
  (Loading savegame in main menu will load automatically "default")
- Saves are in save/ directory

- All game current state (maps, player, environments) are in a roaming buffer (save/roaming), for the sake of a more unified/compact design.
(It grants several advantages: after travelling from portal A to portal B, the world stays persistent/consistent e.i changes are maintained when you come back to portal A...etc)

- World management is done, we can later design different maps by modifying map_i file in data/dev_game/world for instance
  Several cases are available in map_0, and an other map is available map_1 which is linked to map_0 to showcase the "teleport through portals" feature.
  Other maps (map_2 to map_7) can be linked together as well by simply adding the correct portals on the map.

- Game data is relative to a "story game" (each one has their own maps/environments...etc)
  They are located in data/ directory
  Two "stories" are available for the moment:
  * default : base game that will be further developed
  (* dev_game : developer's version of the game to debug, test features...etc which was removed from "production version")

