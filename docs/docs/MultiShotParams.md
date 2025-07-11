---
tags:
  - Class
---
# Class "MultiShotParams"

???+ info
    **[MultiShotParams](MultiShotParams.md)** contains information the game uses to properly calculate the position and velocity of every tear fired, among other things.
    
    你可以通过以下函数获取此类:

    * [EntityPlayer:GetMultiShotParams](EntityPlayer.md#getmultishotparams)

    ???+ example "Example Code"
        ```lua
        local params = Game():GetPlayer(0):GetMultiShotParams(WeaponType.WEAPON_TEARS)
        ```


## Functions

### GetMultiEyeAngle () {: aria-label='Functions' }
#### float GetMultiEyeAngle ( ) {: .copyable aria-label='Functions' }
When more than one eye is active, defines the angle the eyes are offset to eachother. Similar to cross eye effect.
Example: for The Wiz, this is `45`.

### GetNumEyesActive () {: aria-label='Functions' }
#### int GetNumEyesActive ( ) {: .copyable aria-label='Functions' }
Returns the number of eyes simultaniously shooting. Examples: For The Wiz, its `2`, for mutant Spider its `1`.

### GetNumLanesPerEye () {: aria-label='Functions' }
#### int GetNumLanesPerEye ( ) {: .copyable aria-label='Functions' }
Returns the amount of lanes used to spread the shot tears onto.
Normally the number of lanes should be the same number as the amount of tears divided by the number of eyes.
A smaller number of lanes than the amount of tears will cause tears to overlap each other. A higher lane count than tears will make the fan pattern asymetrical.
Lane positions are calculated by dividing the area, defined by the shooting direction +- the spreadAngle, by the number of lanes. This will create a pattern similar to a symetrical hand fan.

### GetNumRandomDirTears () {: aria-label='Functions' }
#### int GetNumRandomDirTears ( ) {: .copyable aria-label='Functions' }
Returns the amount of tears additionally shot in random directions. Same effect as "Eye Sore" collectible.

### GetNumTears () {: aria-label='Functions' }
#### int GetNumTears ( ) {: .copyable aria-label='Functions' }
Returns the amount of tears the player can currently simultaneously fire.

### GetSpreadAngle () {: aria-label='Functions' }
#### float GetSpreadAngle ( [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html) WeaponType ) {: .copyable aria-label='Functions' }
Get the spread angle for the given [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html).

### IsCrossEyed () {: aria-label='Functions' }
#### boolean IsCrossEyed ( ) {: .copyable aria-label='Functions' }
Returns if a cross eye effect is active, aka. player shoots in two directions with 45° offset to eachother.

### IsShootingBackwards () {: aria-label='Functions' }
#### boolean IsShootingBackwards ( ) {: .copyable aria-label='Functions' }
Returns if an additional shot backwards will be triggered. Similar effect to Mom's Eye.

### IsShootingSideways () {: aria-label='Functions' }
#### boolean IsShootingSideways ( ) {: .copyable aria-label='Functions' }
Returns if two additional shots sideways will be triggered. Similar effect to Loki's horns.

### SetIsCrossEyed () {: aria-label='Functions' }
#### void SetIsCrossEyed ( boolean Value ) {: .copyable aria-label='Functions' }
Set if a cross eye effect is active, aka. player shoots in two directions with 45° offset to eachother.

### SetIsShootingBackwards () {: aria-label='Functions' }
#### void SetIsShootingBackwards ( boolean Value ) {: .copyable aria-label='Functions' }
Set if an additional shot backwards will be triggered. Similar effect to Mom's Eye.

### SetIsShootingSideways () {: aria-label='Functions' }
#### void SetIsShootingSideways ( boolean Value ) {: .copyable aria-label='Functions' }
Set if two additional shots sideways will be triggered. Similar effect to Loki's horns.

### SetMultiEyeAngle () {: aria-label='Functions' }
#### void SetMultiEyeAngle ( float Angle ) {: .copyable aria-label='Functions' }
When more than one eye is active, defines the angle the eyes are offset to eachother. Similar to cross eye effect.
Example: for The Wiz, this is `45`.

### SetNumEyesActive () {: aria-label='Functions' }
#### void SetNumEyesActive ( int Value ) {: .copyable aria-label='Functions' }
Set the number of eyes simultaniously shooting. Examples: For The Wiz, its `2`, for mutant Spider its `1`.

### SetNumLanesPerEye () {: aria-label='Functions' }
#### void SetNumLanesPerEye ( int Value ) {: .copyable aria-label='Functions' }

___
### SetNumRandomDirTears () {: aria-label='Functions' }
#### void SetNumRandomDirTears ( int Value ) {: .copyable aria-label='Functions' }
Set the amount of tears additionally shot in random directions. Same effect as "Eye Sore" collectible.

### SetNumTears () {: aria-label='Functions' }
#### void SetNumTears ( int Value ) {: .copyable aria-label='Functions' }
Set the amount of tears the player can currently simultaneously fire.

### SetSpreadAngle () {: aria-label='Functions' }
#### void SetSpreadAngle ( [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html) WeaponType, float Angle ) {: .copyable aria-label='Functions' }
Set the spread angle for the given [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html).
