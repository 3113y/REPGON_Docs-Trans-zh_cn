---
tags:
  - Class
---
# Class "RoomConfigStage"

???+ info
    你可以通过以下函数获取此类:

    - [RoomConfig.GetStage()](RoomConfig.md#getstage)
    
    ???+ example "Example Code"
        ```lua
        local roomConfigStage = RoomConfig.GetStage(StbType.BASEMENT)
        ```

## Functions

### GetBackdrop () {: aria-label='Functions' }
#### [BackdropType](https://wofsauge.github.io/IsaacDocs/rep/enums/BackdropType.html?h=backdrop) GetBackdrop ( ) {: .copyable aria-label='Functions' }
Returns the `BackdropType` used in default rooms on the stage.

### GetBossSpot () {: aria-label='Functions' }
#### string GetBossSpot ( ) {: .copyable aria-label='Functions' }
Returns the sprite path for the boss spot used in the boss intro.

### GetDisplayName () {: aria-label='Functions' }
#### string GetDisplayName ( ) {: .copyable aria-label='Functions' }
Returns the name of the stage.

### GetMusic () {: aria-label='Functions' }
#### [Music](https://wofsauge.github.io/IsaacDocs/rep/enums/Music.html?h=music) GetMusic ( ) {: .copyable aria-label='Functions' }
Returns the `Music` used in default rooms on the stage.

### GetPlayerSpot () {: aria-label='Functions' }
#### string GetPlayerSpot ( ) {: .copyable aria-label='Functions' }
Returns the sprite path for the player spot used in the boss intro and nightmare transition.

### GetRoomSet () {: aria-label='Functions' }
#### [RoomConfigSet](CcpContainer_RoomConfigSet.md) GetRoomSet ( int Mode ) {: .copyable aria-label='Functions' }
Returns a [RoomConfigSet](CcpContainer_RoomConfigSet.md), which contains every [RoomConfigRoom](https://wofsauge.github.io/IsaacDocs/rep/RoomConfig_Room.html) in the stage.
`Mode` is `0` for Normal Mode, `1` for Greed Mode

### GetSuffix () {: aria-label='Functions' }
#### string GetSuffix ( ) {: .copyable aria-label='Functions' }
Returns the suffix used by the stage for stage-unique sprites, such as the boss/player spot and unique variants for enemies.

### SetBackdrop () {: aria-label='Functions' }
#### void SetBackdrop ( [BackdropType](https://wofsauge.github.io/IsaacDocs/rep/enums/BackdropType.html?h=backdrop) Backdrop ) {: .copyable aria-label='Functions' }
Sets the `BackdropType` used in default rooms on the stage.

### SetBossSpot () {: aria-label='Functions' }
#### void SetBossSpot ( string PngFilename ) {: .copyable aria-label='Functions' }
Sets the sprite path for the boss spot used in the boss intro.

### SetDisplayName () {: aria-label='Functions' }
#### void SetDisplayName ( string Name ) {: .copyable aria-label='Functions' }
Sets the name of the stage.

### SetMusic () {: aria-label='Functions' }
#### void SetMusic ( [Music](https://wofsauge.github.io/IsaacDocs/rep/enums/Music.html?h=music) Music ) {: .copyable aria-label='Functions' }
Sets the `Music` used in default rooms on the stage.

### SetPlayerSpot () {: aria-label='Functions' }
#### void SetPlayerSpot ( string PngFilename ) {: .copyable aria-label='Functions' }
Sets the sprite path for the player spot used in the boss intro and nightmare transition.

### SetSuffix () {: aria-label='Functions' }
#### void SetSuffix ( string Suffix ) {: .copyable aria-label='Functions' }
Sets the suffix used by the stage for stage-unique sprites, such as the boss/player spot and unique variants for enemies.
