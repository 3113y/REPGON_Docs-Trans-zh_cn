---
tags:
  - Class
---
# Class "LevelGenerator"

???+ info
    This class gives access to the level generator, the tool that generates a floor.
    
    This class cannot be instanciated. The only way to access it is through callback parameters.

    * [MC_POST_LEVEL_LAYOUT_GENERATED](enums/ModCallbacks.md#mc_post_level_layout_generated)

## Functions

### GetAllRooms () {: aria-label='Functions' }
#### [LevelGeneratorRoom](LevelGeneratorRoom.md)[] GetAllRooms ( ) {: .copyable aria-label='Functions' }
Returns a table of [LevelGeneratorRoom](LevelGeneratorRoom.md) representing all the rooms that have been generated so far.

### GetDeadEnds () {: aria-label='Functions' }
#### [LevelGeneratorRoom](LevelGeneratorRoom.md)[] GetDeadEnds ( ) {: .copyable aria-label='Functions' }
Returns a table of [LevelGeneratorRoom](LevelGeneratorRoom.md) representing all the dead end rooms that have been generated so far.

### GetNonDeadEnds () {: aria-label='Functions' }
#### [LevelGeneratorRoom](LevelGeneratorRoom.md)[] GetNonDeadEnds ( ) {: .copyable aria-label='Functions' }
Returns a table of [LevelGeneratorRoom](LevelGeneratorRoom.md) representing all the non dead end rooms that have been generator so far.

### PlaceRoom () {: aria-label='Functions' }
#### int PlaceRoom ( int Column, int Row, [RoomShape](https://wofsauge.github.io/IsaacDocs/rep/enums/RoomShape.html) Shape, [LevelGeneratorRoom](LevelGeneratorRoom.md) Origin ) {: .copyable aria-label='Functions' }
???+ note "Multiple origins"
When placing a room, you may be wondering which of its neighbors must act as the origin. This has consequences on the placement of special
The column and row values need to be between `0` and `12` (inclusive).
rooms, as the game places special rooms in a specific order based on the distance between each dead end room and the start of the floor.
The `Origin` parameter is used to ensure consistency with the existing rooms. During the generation phase, the game always picks a room 
Place a [LevelGeneratorRoom](LevelGeneratorRoom.md) object onto the level-grid.
In practice you are free to chose any neighboring room as a point of origin.
The `Origin` parameter is used to ensure consistency with the existing rooms. During the generation phase, the game always picks a room
The `Origin` parameter is used as the index of the connecting room. For instance, if you want to place a room on top of the starting room, then `Origin` can be the starting room of the floor.
and starts placing rooms around it. This parameter reflects this behavior.
The distance from the start of the floor of the new room is equal to the distance from the start of the floor of `Origin` plus one.
Returns the GenerationIndex of the placed room. If placement was not possible, returns nil.
