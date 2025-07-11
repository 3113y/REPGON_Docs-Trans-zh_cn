---
tags:
  - Class
---
# Class "GridEntity"

## Modified Functions
### ToTNT () {: aria-label='Modified Functions' }
#### [GridEntityTNT](https://wofsauge.github.io/IsaacDocs/rep/GridEntityTNT.html) ToTNT ( ) {: .copyable aria-label='Modified Functions' }
Altered function to improve GridEntity Update callback behavior.

### GetRenderPosition () {: aria-label='Functions' }
#### [Vector](Vector.md) GetRenderPosition ( ) {: .copyable aria-label='Functions' }

___
### HurtDamage () {: aria-label='Functions' }
#### void HurtDamage ( [Entity](Entity.md) Entity, int PlayerDamage, int DamageFlags, float Damage, boolean ignoreGridCollision ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
The value passed to the float Damage parameter (the intended damage amount to non-player entities) is currently ignored - will be fixed in a future update.

### IsBreakableRock () {: aria-label='Functions' }
#### void IsBreakableRock ( ) {: .copyable aria-label='Functions' }

___
### ToDecoration () {: aria-label='Functions' }
#### [GridEntityDecoration](GridEntityDecoration.md) ToDecoration ( ) {: .copyable aria-label='Functions' }
Used to cast a [GridEntity](GridEntity.md) object to a [GridEntityDecoration](GridEntityDecoration.md) object.
???+ note "Return behavior"
If the conversion is not successful, this function returns `nil`.

### ToFire () {: aria-label='Functions' }
#### [GridEntityFire](GridEntityFire.md) ToFire ( ) {: .copyable aria-label='Functions' }
Used to cast a [GridEntity](GridEntity.md) object to a [GridEntityFire](GridEntityFire.md) object.
If the conversion is not successful, this function returns `nil`.
???+ note "Return behavior"

### ToGravity () {: aria-label='Functions' }
#### [GridEntityGravity](GridEntityGravity.md) ToGravity ( ) {: .copyable aria-label='Functions' }
???+ note "Return behavior"
If the conversion is not successful, this function returns `nil`.
Used to cast a [GridEntity](GridEntity.md) object to a [GridEntityGravity](GridEntityGravity.md) object.

### ToLock () {: aria-label='Functions' }
#### [GridEntityLock](GridEntityLock.md) ToLock ( ) {: .copyable aria-label='Functions' }
Used to cast a [GridEntity](GridEntity.md) object to a [GridEntityLock](GridEntityLock.md) object.
???+ note "Return behavior"
If the conversion is not successful, this function returns `nil`.

### ToStairs () {: aria-label='Functions' }
#### [GridEntityStairs](GridEntityStairs.md) ToStairs ( ) {: .copyable aria-label='Functions' }
???+ note "Return behavior"
If the conversion is not successful, this function returns `nil`.
Used to cast a [GridEntity](GridEntity.md) object to a [GridEntityStairs](GridEntityStairs.md) object.

### ToStatue () {: aria-label='Functions' }
#### [GridEntityStatue](GridEntityStatue.md) ToStatue ( ) {: .copyable aria-label='Functions' }
???+ note "Return behavior"
If the conversion is not successful, this function returns `nil`.
Used to cast a [GridEntity](GridEntity.md) object to a [GridEntityStatue](GridEntityStatue.md) object.

### ToTeleporter () {: aria-label='Functions' }
#### [GridEntityTeleporter](GridEntityTeleporter.md) ToTeleporter ( ) {: .copyable aria-label='Functions' }   
Used to cast a [GridEntity](GridEntity.md) object to a [GridEntityTeleporter](GridEntityTeleporter.md) object.
???+ note "Return behavior"
If the conversion is not successful, this function returns `nil`.

### ToTrapDoor () {: aria-label='Functions' }
#### [GridEntityTrapDoor](GridEntityTrapDoor.md) ToTrapDoor ( ) {: .copyable aria-label='Functions' }
???+ note "Return behavior"
Used to cast a [GridEntity](GridEntity.md) object to a [GridEntityTrapDoor](GridEntityTrapDoor.md) object.
If the conversion is not successful, this function returns `nil`.

### ToWall () {: aria-label='Functions' }
#### [GridEntityWall](GridEntityWall.md) ToWall ( ) {: .copyable aria-label='Functions' }
Used to cast a [GridEntity](GridEntity.md) object to a [GridEntityWall](GridEntityWall.md) object.
???+ note "Return behavior"
If the conversion is not successful, this function returns `nil`.

### ToWeb () {: aria-label='Functions' }
#### [GridEntityWeb](GridEntityWeb.md) ToWeb ( ) {: .copyable aria-label='Functions' }
Used to cast a [GridEntity](GridEntity.md) object to a [GridEntityWeb](GridEntityWeb.md) object.
???+ note "Return behavior"
If the conversion is not successful, this function returns `nil`.
