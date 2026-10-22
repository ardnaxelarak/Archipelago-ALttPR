Some notes on how door shuffle works.

Doors can connect to random rooms, and can be randomized to be any of the following types: open, small key locked, big key locked, bombable, dash-or-bombable, and one-way traps. Big key and trap doors are only shuffled with some door_type_shuffle settings. The exact number of each door type is always the same, unless door_type_shuffle is set to chaos, where it can vary slightly (-1 to +4).

In general, both sides of a door will be the same type, except for trap doors, and unlocking one side of a door will always unlock the other side. It is possible for two spiral staircases to be connected where one of them is key-locked, and the other is open.

Doors will always roughly line up with each other; north-facing doors connect to south-facing doors, etc.

## Kinds of Doors
### Normal
Doors connecting two supertiles that Link can walk through. Fully randomized.

### Interior
Doors that connect two rooms within the same supertile. They always connect to the same room as vanilla, but their type (small key locked, bombable, etc.) is fully randomized.

### Straight Stairs
Doors with a staircase leading straight up or down. These connect to a random room, but are always open.

### Hole
A dropdown to another room. Never randomized. Both rooms are always in the same dungeon, which might not be vanilla.

### Warp
Warp tiles. Never randomized. Both rooms are always in the same dungeon, which might not be vanilla.

### Trap (Openable)
Impassible doors which can be opened by killing all the enemies, pressing a switch, or some other condition. Can connect to a random room, if they are on the edge of a supertile, but they are always a openable trap door. The other side of the trap door can be randomized.

### Trap (One-way)
Can only be traversed in one direction, such as Skull pinball room west or the Sewers leading back to Hyrule Castle. These are only randomized depending on the door_type_shuffle setting. If randomized, every room of the dungeon will be accessible, although dead ends are allowed.

### Spiral Stairs
Doors with a spiral staircase. Can only connect to other spiral staircases, and will always be either open or small key locked. Only spiral stairs that are key locked in vanilla can be key locked in door shuffle; this can lead to one side of a staircase being key locked while the other side is open.

### Ladder
Staircases in the middle of the room, such as the one leading to PoD basement, or right after GT torches on the climb. These connect to a random room, and are always open.

### Open
Open edges, like every exit from the Desert Palace lobby. These connect to a random room in the direction you'd expect, and are always open.

### Logical
Not a real door, but included for logic, e.g. Hyrule Castle Cellblock Door. Never randomized.

## Non-implemented options
These are options available in OWR, but not implemented in AP. In general I don't plan to add these, but I thought I'd mention them for completion's sake.

* Decoupled doors. Probably the most likely to be added eventually
* Not randomizing open edges, straight staircases, and ladders. Originally I forced it on to both keep things simpler for testing, and to not flood the YAML with options. Maybe this could be added, but also, if you want doors, you probably want maximum doors (within reason)
* Options for removing boss trap doors or "annoying" trap doors. More so than the last one, it's flooding the YAML for a weird feature that I doubt anyone cares about
* Self-looping spiral staircases. I guess it's kinda funny, but it also makes the dungeons less complex.
* Prevent/allow mixed travel; in AP rails are always added in three locations to prevent glitching into another dungeon (hammerjump, PoD arena hover to ledge, Mire bomb jump from cutscene chest to the above railing). There are options to force the two sections to be in the same dungeon (again, reducing randomness for little/no gain), or to allow glitching into another dungeon, which could VERY easily make a seed unbeatable.

## Exceptions
The north Sanctuary exit is always one-way. The vines in Skull and the curtain near the top of Aga Tower are always there and require a sword to exit through the blocked doors. A sword is not required when entering those rooms from the north.

There are certain big key doors that look ugly as a small key locked door, so they are never small key locked. Not 100% sure what's going on here tbh, but that's what the description said.
* Eastern Hint Tile Blocked Path SE
* Eastern Darkness S
* Thieves Hallway SE
* Mire Left Bridge S
* TR Lava Escape SE
* GT Hidden Spikes SE


Normal and interior doors have a door position, 0-7, with doors in the same room having a different position to differenciate them. However, the vanilla game only keeps track of door states (whether a key door has been unlocked, etc.) for positions 0-3, so any door in position 4+ is always open. Doors in position 3 also cannot be trap doors, although I'm not sure why that was done.

Doors in position 3:
* Hyrule Castle West Lobby EN
* Hyrule Castle East Lobby N
* Eastern Lobby NE
* Eastern Lobby Right Ledge SE
* Eastern Cannonball Ledge WN
* Eastern East Wing ES
* Eastern Map Balcony WS
* Eastern Compass Room EN
* Eastern Hint Tile WN
* Eastern Courtyard WN
* Desert East Lobby WS
* Desert East Wing ES
* Tower Lobby S
* PoD Lobby N
* PoD Middle Cage S
* PoD Arena Crystals E
* PoD Sexy Statue W
* PoD Falling Bridge SW
* Swamp Trench 1 Approach ES
* Swamp Hub WS
* Swamp Crystal Switch SE
* Swamp Shortcut NE
* Swamp Shooters EN
* Swamp Left Elbow WN
* Swamp Waterfall Room NW
* Swamp Refill SW
* Swamp T NW
* Skull Pot Circle WN
* Skull Pull Switch EN
* Skull 2 East Lobby SW
* Skull Small Hall ES
* Skull East Bridge WS
* Skull West Bridge Nook ES
* Skull Star Pits ES
* Skull Torch Room WS
* Thieves Pot Alcove Bottom SW
* Thieves Spike Track NE
* Thieves Triple Bypass SE
* Thieves Lonely Zazak ES
* s Cell WS
* Thieves Conveyor Bridge ES
* Ice Cross Bottom SE
* Ice Spike Cross WS
* Ice Firebar ES
* Ice Crystal Right ES
* Mire Hub WN
* Mire Lone Shooter ES
* Mire Falling Bridge WS
* Mire BK Door Room EN
* Mire Spikes WS
* Mire Right Bridge SE
* Mire Spike Barrier ES
* Mire Square Rail WS
* Mire Tile Room NW
* Mire Compass Room SW
* Mire Neglected Room SE
* Mire Chest View NE
* Mire Tall Dark and Roomy WS
* Mire Crystal Right ES
* TR Hub ES
* TR Pokey 1 NW
* TR Chain Chomps SW
* TR Lava Dual Pipes WN
* TR Big Chest NE
* TR Dodgers SE
* TR Tongue Pull NE
* TR Rupees SE
* GT Torch WN
* GT Speed Torch NE
* GT Invisible Catwalk WS
* GT Hookshot SW
* GT Falling Bridge WS
* GT Crystal Paths SW
* GT Mimics 1 NW
* GT Bomb Conveyor SW
* GT Crystal Circles NW


Doors in position 4+:

* Hyrule Castle Lobby S
* Eastern Lobby S
* Eastern Courtyard Ledge S
* Eastern East Wing W
* Eastern West Wing E
* Eastern Hint Tile EN
* Eastern Courtyard EN
* Eastern Map Valley SW
* PoD Lobby S
* PoD Arena Main SW
* PoD Arena Bridge SE
* PoD Falling Bridge EN
* PoD Compass Room WN
* PoD Harmless Hellway SE
* Swamp Trench 1 Nexus N
* Swamp Trench 1 Alcove S
* Swamp Trench 1 Departure WS
* Swamp Hub ES
* Swamp Hub S
* Swamp Trench 2 Pots ES
* Swamp Trench 2 Blocks N
* Swamp Trench 2 Alcove S
* Skull 1 Lobby S
* Skull 1 Lobby ES
* Skull Map Room WS
* Skull Pot Prison SE
* Skull 2 East Lobby WS
* Thieves Hallway NE
* Thieves Pot Alcove Mid WS
* Thieves Conveyor Maze WN
* Thieves Conveyor Maze SW
* Thieves Pot Alcove Top NW
* Thieves Spike Track ES
* Thieves Triple Bypass EN
* Mire Hub SE
* Mire Hub ES
* Mire Hub E
* Mire Hub NE
* Mire Lone Shooter WS
* Mire Failure Bridge W
* Mire Crystal Dead End NW
* Mire Hidden Shooters SE
* Mire Hidden Shooters ES
* Mire Cross SW
* Mire Minibridge NE
* Mire Spikes SW
* Mire Wizzrobe Bypass EN
* Mire Wizzrobe Bypass NE
* Mire Conveyor Crystal SE
* Mire Tile Room SW
* Mire Tall Dark and Roomy ES
* TR Hub SW
* TR Hub SE
* TR Tile Room SE
* TR Lava Dual Pipes EN
* TR Lava Dual Pipes SW
* TR Lava Island ES
* TR Twin Pokeys NW
* TR Hallway WS
* TR Hallway ES
* TR Big View WS
* TR Big Chest Entrance SE
* TR Dash Room SW
* GT Big Chest SW
* GT Bob's Room SE
* GT Speed Torch WS
* GT Pots n Blocks ES
* GT Hookshot NW
