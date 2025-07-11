---
tags:
  - Class
---
# Class "Room"
## Modified Functions

### GetBackdropType () {: aria-label='Modified Functions' }
#### [BackdropType](https://wofsauge.github.io/IsaacDocs/rep/enums/BackdropType.html) GetBackdropType ( ) {: .copyable aria-label='Modified Functions' }

___
### GetLRoomAreaDesc () {: aria-label='Modified Functions' }
#### [LRoomAreaDesc](LRoomAreaDesc.md) GetLRoomAreaDesc ( ) {: .copyable aria-label='Modified Functions' }
Now returns a usable class. Describes the corners of an L-room shape (as divided horizontally into two rectangles), in worldspace.

### GetLRoomTileDesc () {: aria-label='Modified Functions' }
#### [LRoomTileDesc](LRoomTileDesc.md) GetLRoomTileDesc ( ) {: .copyable aria-label='Modified Functions' }
Now returns a usable class. Describes the corners of an L-room shape (as divided horizontally into two rectangles), in grid coordinates.

### SpawnGridEntity () {: aria-label='Modified Functions' }
#### boolean SpawnGridEntity ( int GridIndex, [GridEntityType](https://wofsauge.github.io/IsaacDocs/rep/enums/GridEntityType.html) Type, int Variant = 0, int Seed = nil, int VarData = 0 ) {: .copyable aria-label='Modified Functions' }
No longer crashes if an invalid `GridIndex` is used. All arguments beyond `Type` are optional. An overload has been added to allow spawning a new grid entity using an existing `GridEntityDesc`.

### TrySpawnSpecialQuestDoor () {: aria-label='Modified Functions' }
#### boolean TrySpawnSpecialQuestDoor ( boolean IgnoreStageType = false ) {: .copyable aria-label='Modified Functions' }
An `IgnoreStageType` parameter has been added to allow spawning the Mirror & Mineshaft door outside of `STAGETYPE_REPENTANCE` and `STAGETYPE_REPENTANCE_B` stages. Note that the `KNIFE_PUZZLE` [dimension](Level.md?#dimension-getdimension) must be set up properly for these doors not to crash on entry!

### CanPickupGridEntity () {: aria-label='Functions' }
#### boolean CanPickupGridEntity ( int GridIndex ) {: .copyable aria-label='Functions' }
Returns true if the gridentity at the given position can be picked up.

### CanSpawnObstacleAtPosition () {: aria-label='Functions' }
#### boolean CanSpawnObstacleAtPosition ( int GridIndex, boolean Force ) {: .copyable aria-label='Functions' }

___
### DoLightningStrike () {: aria-label='Functions' }
#### void DoLightningStrike ( int Seed = RandomSeed ) {: .copyable aria-label='Functions' }
Creates a lightning effect as seen in Downpour. `Seed` determines [intensity](Room.md#getlightningintensity) (`1.3 + RandomFloat()*.6`) and sound pitch (`0.9 + RandomFloat()*0.2`).

### GetBackdrop () {: aria-label='Functions' }
#### [Backdrop](Backdrop.md) GetBackdrop ( ) {: .copyable aria-label='Functions' }
Returns a [Backdrop](Backdrop.md) object.

### GetBossVictoryJingle () {: aria-label='Functions' }
#### [Music](https://wofsauge.github.io/IsaacDocs/rep/enums/Music.html) GetBossVictoryJingle ( ) {: .copyable aria-label='Functions' }

___
### GetCamera () {: aria-label='Functions' }
#### [Camera](Camera.md) GetCamera ( ) {: .copyable aria-label='Functions' }
Returns a [Camera](Camera.md) object.

### GetChampionBossChance () {: aria-label='Functions' }
#### float GetChampionBossChance ( ) {: .copyable aria-label='Functions' }
Return the probability that boss spawns in this room will be champions.

### GetEffects () {: aria-label='Functions' }
#### [TemporaryEffects](https://wofsauge.github.io/IsaacDocs/rep/TemporaryEffects.html) GetEffects ( ) {: .copyable aria-label='Functions' }

___
### GetFloorColor () {: aria-label='Functions' }
#### [Color](Color.md) GetFloorColor ( ) {: .copyable aria-label='Functions' }

___
### GetFXParams () {: aria-label='Functions' }
#### [FXParams](FXParams.md) GetFXParams ( ) {: .copyable aria-label='Functions' }

___
### GetGreedWaveTimer () {: aria-label='Functions' }
#### int GetGreedWaveTimer ( ) {: .copyable aria-label='Functions' }

___
### GetGridIndexByTile () {: aria-label='Functions' }
#### int GetGridIndexByTile ( int GridRow, int GridColumn ) {: .copyable aria-label='Functions' }
#### int GetGridIndexByTile ( int[2] Tile ) {: .copyable aria-label='Functions' }

___
### GetItemPool () {: aria-label='Functions' }
#### [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) PoolType GetItemPool ( int Seed, boolean Raw ) {: .copyable aria-label='Functions' }
If `Raw` is set to `true` and the pool is set to `POOL_NULL` then `POOL_NULL` will be returned, instead of running the game's pool selection code.
Retrieves the [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) the game would use to generate random collectibles in the current room. Unlike [ItemPool.GetPoolForRoom()](https://wofsauge.github.io/IsaacDocs/rep/ItemPool.html#getpoolforroom), this takes into account the pool set using [SetItemPool()](Room.md#setitempool), and runs the game's pool selection code, which handles unique cases (ex. Boss Room + Used Satanic Bible = Devil Pool).

### GetLightningIntensity () {: aria-label='Functions' }
#### float GetLightningIntensity ( ) {: .copyable aria-label='Functions' }
This is set by the game in a random range between `1.3` and `2.1`, and decays by `value * .75` per render.
Gets the intensity of the lightning effect used in Downpour. This variable will affect the visibility of Wraiths.

### GetNumRainSpawners () {: aria-label='Functions' }
#### int GetNumRainSpawners ( ) {: .copyable aria-label='Functions' }
???+ info
There's more to this than just the number of them, but I'm having trouble identifying how this works.
The number of areas in a room that spawn rain effects in a tight radius.

### GetRail () {: aria-label='Functions' }
#### [StbRailVariant](enums/StbRailVariant.md) GetRail ( int GridIndex ) {: .copyable aria-label='Functions' }

___
### GetRailManager () {: aria-label='Functions' }
#### [RailManager](RailManager.md) GetRailManager ( ) {: .copyable aria-label='Functions' }

___
### GetRainIntensity () {: aria-label='Functions' }
#### float GetRainIntensity ( ) {: .copyable aria-label='Functions' }
Used by the positional rain effect spawners in Downpour. No noticable effect beyond `1.0`.

### GetRoomClearDelay () {: aria-label='Functions' }
#### int GetRoomClearDelay ( ) {: .copyable aria-label='Functions' }

___
### GetShopItemPrice () {: aria-label='Functions' }
#### int GetShopItemPrice ( int EntityVariant, int EntitySubType, int ShopItemID ) {: .copyable aria-label='Functions' }
Returns the price of the item.

### GetWaterAmount () {: aria-label='Functions' }
#### float GetWaterAmount ( ) {: .copyable aria-label='Functions' }
Returns the "amount" of water currently in the room. Generally this will be `0` for no water and `1` for water, but values in between `0` and `1` (and technically above `1` in modded scenarios) are possible.

### GetWaterColor () {: aria-label='Functions' }
#### [KColor](https://wofsauge.github.io/IsaacDocs/rep/KColor.html) GetWaterColor ( ) {: .copyable aria-label='Functions' }

___
### GetWaterColorMultiplier () {: aria-label='Functions' }
#### [KColor](https://wofsauge.github.io/IsaacDocs/rep/KColor.html) GetWaterColorMultiplier ( ) {: .copyable aria-label='Functions' }

___
### IsChampionBossSeed () {: aria-label='Functions' }
#### boolean IsChampionBossSeed ( ) {: .copyable aria-label='Functions' }
Return whether boss spawns in this room will be champions.

### IsPersistentRoomEntity () {: aria-label='Functions' }
#### boolean IsPersistentRoomEntity ( [EntityType](https://wofsauge.github.io/IsaacDocs/rep/enums/EntityType.html) Type, int Variant = 0 ) {: .copyable aria-label='Functions' }

___
### PickupGridEntity () {: aria-label='Functions' }
#### [EntityEffect](https://wofsauge.github.io/IsaacDocs/rep/EntityEffect.html) PickupGridEntity ( int GridIndex ) {: .copyable aria-label='Functions' }
Tries to pick up the grid entity at the provided index and returns an [EntityEffect](https://wofsauge.github.io/IsaacDocs/rep/EntityEffect.html) of the picked up grid entity.

### RemoveGridEntityImmediate () {: aria-label='Functions' }
#### void RemoveGridEntityImmediate ( int GridIndex, int PathTrail, boolean KeepDecoration ) {: .copyable aria-label='Functions' }
*Immediately* removes the GridEntity at the given index. This means grids can be properly removed and immediately replaced, *without* the need to call Room:Update.

### SaveState () {: aria-label='Functions' }
#### void SaveState ( ) {: .copyable aria-label='Functions' }
Saves the current state of the room

### SetBackdropType () {: aria-label='Functions' }
#### void SetBackdropType ( [BackdropType](https://wofsauge.github.io/IsaacDocs/rep/enums/BackdropType.html), int Unknown ) {: .copyable aria-label='Functions' }
The backdrop variant chosen is seeded based on the room, and does not persist when leaving and re-entering. Calling this function again on re-entry will result in the same backdrop variant as before.
This function will not work if the Unknown integer is passed as `0`.

### SetGreedWaveTimer () {: aria-label='Functions' }
#### void SetGreedWaveTimer ( int Time ) {: .copyable aria-label='Functions' }

___
### SetItemPool () {: aria-label='Functions' }
#### void SetItemPool ( [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) PoolType ) {: .copyable aria-label='Functions' }
Sets the pool to use when the game needs to generate random collectibles in the current room. This takes priority over the game's regular pool selection code. Can be set to `ItemPoolType.POOL_NULL` to let the game handle pool selection. This is reset every room transition.

### SetLavaIntensity () {: aria-label='Functions' }
#### void SetLavaIntensity ( float Intensity ) {: .copyable aria-label='Functions' }
This primarily affects [UpdateColorModifier](Room.md#updatecolormodifier) (if `Process` is true, an orange glow is added based on the number of pits and lava intensity).

### SetLightningIntensity () {: aria-label='Functions' }
#### void SetLightningIntensity ( float Intensity ) {: .copyable aria-label='Functions' }
Sets the intensity of the lightning effect used in Downpour. This variable will affect the visibility of Wraiths.
This is set by the game in a random range between `1.3` and `2.1`, and decays by `value * .75` per render.

### SetPauseTimer () {: aria-label='Functions' }
#### void SetPauseTimer ( int Duration ) {: .copyable aria-label='Functions' }

___
### SetRail () {: aria-label='Functions' }
#### void SetRail ( int GridIndex, [StbRailVariant](enums/StbRailVariant.md) RailVariant ) {: .copyable aria-label='Functions' }

___
### SetRainIntensity () {: aria-label='Functions' }
#### void SetRainIntensity ( float Intensity ) {: .copyable aria-label='Functions' }
Used by the positional rain effect spawners in Downpour. No noticable effect beyond `1.0`.

### SetRoomClearDelay () {: aria-label='Functions' }
#### void SetRoomClearDelay ( int Delay ) {: .copyable aria-label='Functions' }

___
### SetWaterAmount () {: aria-label='Functions' }
#### void SetWaterAmount ( float Amount ) {: .copyable aria-label='Functions' }
Sets the amount of water that should be in the current room. Vanilla typically uses `0` for no water and `1` for water. You can technically go higher than this for some interesting results.

### SetWaterColor () {: aria-label='Functions' }
#### void SetWaterColor ( [KColor](Color.md) WaterColor ) {: .copyable aria-label='Functions' }

___
### SetWaterColorMultiplier () {: aria-label='Functions' }
#### void SetWaterColorMultiplier ( [KColor](Color.md) WaterColor ) {: .copyable aria-label='Functions' }

___
### SetWaterCurrent () {: aria-label='Functions' }
#### void SetWaterCurrent ( [Vector](Vector.md) WaterCurrent ) {: .copyable aria-label='Functions' }
`Vector(0, 0)` will remove the current.
The game typically uses `1` or `-1` for its values depending on current strength and direction. You can technically go higher than this for some interesting results. Arbitrary directions are fully supported as well.
Sets the strength of the water current in the room. Current sounds and particles are automatically handled.

### TryGetShopDiscount () {: aria-label='Functions' }
#### int TryGetShopDiscount ( int ShopItemIdx, int Price ) {: .copyable aria-label='Functions' }

___
### UpdateColorModifier () {: aria-label='Functions' }
#### void UpdateColorModifier ( boolean Process = true, boolean Lerp = true, float Rate = 0.015 ) {: .copyable aria-label='Functions' }
`Process` runs the color correction through some additional modifications for lava and the abandoned mineshaft sequence.
Updates the room's color correction with the copy of [ColorModifier](ColorModifier.md) stored in [FXParams](FXParams.md).
