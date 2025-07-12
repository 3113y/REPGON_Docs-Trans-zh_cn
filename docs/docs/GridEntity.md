---
tags:
  - Class
---
# Class "GridEntity"

## Modified Functions
### ToTNT () {: aria-label='Modified Functions' }
#### [GridEntityTNT](https://wofsauge.github.io/IsaacDocs/rep/GridEntityTNT.html) ToTNT ( ) {: .copyable aria-label='Modified Functions' }
修改函数以改善网格实体更新回调的行为。

### GetRenderPosition () {: aria-label='Functions' }
#### [Vector](Vector.md) GetRenderPosition ( ) {: .copyable aria-label='Functions' }

___
### HurtDamage () {: aria-label='Functions' }
#### void HurtDamage ( [Entity](Entity.md) Entity, int PlayerDamage, int DamageFlags, float Damage, boolean ignoreGridCollision ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
传递给浮点型Damage参数（对非玩家实体的预期伤害值）的值目前会被忽略，将在未来的更新中修复。

### IsBreakableRock () {: aria-label='Functions' }
#### void IsBreakableRock ( ) {: .copyable aria-label='Functions' }

___
### ToDecoration () {: aria-label='Functions' }
#### [GridEntityDecoration](GridEntityDecoration.md) ToDecoration ( ) {: .copyable aria-label='Functions' }
用于将一个[GridEntity](GridEntity.md)对象转换为一个[GridEntityDecoration](GridEntityDecoration.md)对象。
???+ note "返回行为"
如果转换不成功，此函数返回`nil`。

### ToFire () {: aria-label='Functions' }
#### [GridEntityFire](GridEntityFire.md) ToFire ( ) {: .copyable aria-label='Functions' }
用于将一个[GridEntity](GridEntity.md)对象转换为一个[GridEntityFire](GridEntityFire.md)对象。
如果转换不成功，此函数返回`nil`。
???+ note "返回行为"

### ToGravity () {: aria-label='Functions' }
#### [GridEntityGravity](GridEntityGravity.md) ToGravity ( ) {: .copyable aria-label='Functions' }
???+ note "返回行为"
如果转换不成功，此函数返回`nil`。
用于将一个[GridEntity](GridEntity.md)对象转换为一个[GridEntityGravity](GridEntityGravity.md)对象。

### ToLock () {: aria-label='Functions' }
#### [GridEntityLock](GridEntityLock.md) ToLock ( ) {: .copyable aria-label='Functions' }
用于将一个[GridEntity](GridEntity.md)对象转换为一个[GridEntityLock](GridEntityLock.md)对象。
???+ note "返回行为"
如果转换不成功，此函数返回`nil`。

### ToStairs () {: aria-label='Functions' }
#### [GridEntityStairs](GridEntityStairs.md) ToStairs ( ) {: .copyable aria-label='Functions' }
???+ note "返回行为"
如果转换不成功，此函数返回`nil`。
用于将一个[GridEntity](GridEntity.md)对象转换为一个[GridEntityStairs](GridEntityStairs.md)对象。

### ToStatue () {: aria-label='Functions' }
#### [GridEntityStatue](GridEntityStatue.md) ToStatue ( ) {: .copyable aria-label='Functions' }
???+ note "返回行为"
如果转换不成功，此函数返回`nil`。
用于将一个[GridEntity](GridEntity.md)对象转换为一个[GridEntityStatue](GridEntityStatue.md)对象。

### ToTeleporter () {: aria-label='Functions' }
#### [GridEntityTeleporter](GridEntityTeleporter.md) ToTeleporter ( ) {: .copyable aria-label='Functions' }   
用于将一个[GridEntity](GridEntity.md)对象转换为一个[GridEntityTeleporter](GridEntityTeleporter.md)对象。
???+ note "返回行为"
如果转换不成功，此函数返回`nil`。

### ToTrapDoor () {: aria-label='Functions' }
#### [GridEntityTrapDoor](GridEntityTrapDoor.md) ToTrapDoor ( ) {: .copyable aria-label='Functions' }
???+ note "返回行为"
用于将一个[GridEntity](GridEntity.md)对象转换为一个[GridEntityTrapDoor](GridEntityTrapDoor.md)对象。
如果转换不成功，此函数返回`nil`。

### ToWall () {: aria-label='Functions' }
#### [GridEntityWall](GridEntityWall.md) ToWall ( ) {: .copyable aria-label='Functions' }
用于将一个[GridEntity](GridEntity.md)对象转换为一个[GridEntityWall](GridEntityWall.md)对象。
???+ note "返回行为"
如果转换不成功，此函数返回`nil`。

### ToWeb () {: aria-label='Functions' }
#### [GridEntityWeb](GridEntityWeb.md) ToWeb ( ) {: .copyable aria-label='Functions' }
用于将一个[GridEntity](GridEntity.md)对象转换为一个[GridEntityWeb](GridEntityWeb.md)对象。
???+ note "返回行为"
如果转换不成功，此函数返回`nil`。