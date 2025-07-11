---
tags:
  - Class
---
# Class "EntityNPC"

## Class Diagram
--8<-- "docs/snippets/EntityClassDiagram_NewFunkyMode.md"

## Modified Functions

### PlaySound () {: aria-label='Modified Functions' }
#### void PlaySound ( int ID, float Volume = 1.0, int FrameDelay = 2, boolean Loop = true, float Pitch = 1.0 ) {: .copyable aria-label='Modified Functions' }
除 `ID` 之外的所有参数现在都是可选的。

### ClearFlyingOverride () {: aria-label='Functions' }
#### void ClearFlyingOverride ( ) {: .copyable aria-label='Functions' }
移除由 [SetFlyingOverride](EntityNPC.md#setflyingoverride) 设置的任何值。

### FireBossProjectilesEx () {: aria-label='Functions' }
#### [EntityProjectile](EntityProjectile.md)[] FireBossProjectilesEx ( int NumProjectiles, [Vector](Vector.md) TargetPos, float TrajectoryModifier, [ProjectileParams](https://wofsauge.github.io/IsaacDocs/rep/ProjectileParams.html) Params ) {: .copyable aria-label='Functions' }
与 [FireBossProjectiles](https://wofsauge.github.io/IsaacDocs/rep/EntityNPC.html#firebossprojectiles) 相同，但返回一个包含已生成弹幕列表的表。

### FireGridEntity () {: aria-label='Functions' }
#### [EntityProjectile](EntityProjectile.md) FireGridEntity ( [Sprite](Sprite.md) GridEntitySprite, [GridEntityDesc](https://wofsauge.github.io/IsaacDocs/rep/GridEntityDesc.html) GridEntityDesc, [Vector](Vector.md) Velocity, [BackdropType](https://wofsauge.github.io/IsaacDocs/rep/enums/BackdropType.html) Backdrop = BackdropType.BASEMENT ) {: .copyable aria-label='Functions' }

___
### FireProjectilesEx () {: aria-label='Functions' }
#### [EntityProjectile](EntityProjectile.md)[] FireProjectilesEx ([Vector](Vector.md) Position, [Vector](Vector.md) Velocity, ProjectilesMode Mode, [ProjectileParams](https://wofsauge.github.io/IsaacDocs/rep/ProjectileParams.html) Params) {: .copyable aria-label='Functions' }
与 [FireProjectiles](https://wofsauge.github.io/IsaacDocs/rep/EntityNPC.html#fireprojectiles) 相同，但返回一个包含已生成弹幕列表的表。

### GetBossColorIdx () {: aria-label='Functions' }
#### int GetBossColorIdx ( ) {: .copyable aria-label='Functions' }
返回 bosscoloridx（通常就是子类型），如果不是 bosscolor（或者不适用 bosscolor）则返回 -1。

### GetControllerId () {: aria-label='Functions' }
#### int GetControllerId ( ) {: .copyable aria-label='Functions' }
返回 NPC 的控制器 ID，该 ID 指示哪个玩家正在控制它。当没有被任何玩家控制时将返回 `-1`。

### GetDarkRedChampionRegenTimer () {: aria-label='Functions' }
#### int GetDarkRedChampionRegenTimer ( ) {: .copyable aria-label='Functions' }

___
### GetDirtColor () {: aria-label='Functions' }
#### [Color](Color.md) GetDirtColor ( ) {: .copyable aria-label='Functions' }
返回实体的动态泥土颜色。这可以让像夜行者这样的实体融入环境。

### GetFireplaceLoot () {: aria-label='Functions' }
#### [LootList](LootList.md) GetFireplaceLoot ( ) {: .copyable aria-label='Functions' }
返回壁炉使用的唯一 [LootList](LootList.md)。

### GetHitList () {: aria-label='Functions' }
#### int[] GetHitList ( ) {: .copyable aria-label='Functions' }

___
### GetShieldStrength () {: aria-label='Functions' }
#### float GetShieldStrength ( ) {: .copyable aria-label='Functions' }

___
### GetShopkeeperLoot () {: aria-label='Functions' }
#### [LootList](LootList.md) GetShopkeeperLoot ( ) {: .copyable aria-label='Functions' }
返回店主使用的唯一 [LootList](LootList.md)。

### GetSirenPlayerEntity () {: aria-label='Functions' }
#### [EntityPlayer](EntityPlayer.md) GetSirenPlayerEntity ( ) {: .copyable aria-label='Functions' }

___
### IsBossColor () {: aria-label='Functions' }
#### boolean IsBossColor ( ) {: .copyable aria-label='Functions' }

___
### ReplaceSpritesheet () {: aria-label='Functions' }
#### void ReplaceSpritesheet ( int LayerId, string PngFilename, bool LoadGraphics = false ) {: .copyable aria-label='Functions' }
类似于 [Sprite.ReplaceSpritesheet()](https://wofsauge.github.io/IsaacDocs/rep/Sprite.html#replacespritesheet)。如果可能的话，会在 `PngFilename` 后面追加 "_champion"/阶段后缀。

### SetControllerId () {: aria-label='Functions' }
#### int SetControllerId ( int ControllerId ) {: .copyable aria-label='Functions' }
设置 NPC 的控制器 ID，该 ID 指示哪个玩家将控制它。将其设置为 `-1` 表示没有玩家控制（恢复正常行为）。

### SetFlyingOverride () {: aria-label='Functions' }
#### void SetFlyingOverride ( boolean CanFly ) {: .copyable aria-label='Functions' }
设置对 IsFlying 返回值的覆盖，IsFlying 通常基于 [EntityGridCollisionClass](https://wofsauge.github.io/IsaacDocs/rep/enums/EntityGridCollisionClass.html)。可用于使地面敌人忽略软泥，或使飞行敌人被软泥击中。

### SetShieldStrength () {: aria-label='Functions' }
#### void SetShieldStrength ( float Strength ) {: .copyable aria-label='Functions' }

___
### ShootMaggotProjectile () {: aria-label='Functions' }
#### static const [EntityNPC](EntityNPC.md) ShootMaggotProjectile ( [Vector](Vector.md) Position, [Vector](Vector.md) Target, float FallingSpeed = -8.0, float YOffset = -24.0 ) {: .copyable aria-label='Functions' }

___
### SpawnBloodCloud () {: aria-label='Functions' }
#### [EntityEffect](EntityEffect.md) SpawnBloodCloud ( [Vector](Vector.md) Position, [Color](Color.md) Color ) {: .copyable aria-label='Functions' }

___
### SpawnBloodSplash () {: aria-label='Functions' }
#### void SpawnBloodSplash ( ) {: .copyable aria-label='Functions' }

___
### ThrowLeech () {: aria-label='Functions' }
#### static const [EntityNPC](EntityNPC.md) ThrowLeech ( [Vector](Vector.md) Position, [Entity](Entity.md) Source, [Vector](Vector.md) Target, float YPosOffset = -10.0, boolean Big = false ) {: .copyable aria-label='Functions' }

___
### ThrowMaggot () {: aria-label='Functions' }
#### static const [EntityNPC](EntityNPC.md) ThrowMaggot ( [Vector](Vector.md) Origin, [Vector](Vector.md) Velocity, float YOffset = -10.0, float FallSpeed = -8.0 ) {: .copyable aria-label='Functions' }

___
### ThrowMaggotAtPos () {: aria-label='Functions' }
#### static const [EntityNPC](EntityNPC.md) ThrowMaggotAtPos ( [Vector](Vector.md) Origin, [Vector](Vector.md) Target, float YOffset = -8.0 ) {: .copyable aria-label='Functions' }

___
### ThrowRockSpider () {: aria-label='Functions' }
#### static const [EntityNPC](EntityNPC.md) ThrowRockSpider ( [Vector](Vector.md) Position, [Entity](Entity.md) Source, [Vector](Vector.md) Velocity, int Variant = 0, float YPosOffset = -10.0 ) {: .copyable aria-label='Functions' }

___
### ThrowStrider () {: aria-label='Functions' }
#### static const [EntityNPC](EntityNPC.md) ThrowStrider ( [Vector](Vector.md) Position, [Entity](Entity.md) Source, [Vector](Vector.md) Target ) {: .copyable aria-label='Functions' }

___
### TryForceTarget () {: aria-label='Functions' }
#### boolean TryForceTarget ( [Entity](Entity.md) Target, int Duration ) {: .copyable aria-label='Functions' }
由迷失苍蝇使用，用于强制该 NPC 专注于特定目标。

### TrySplit () {: aria-label='Functions' }
#### boolean TrySplit ( float DefaultDamage, [EntityRef](https://wofsauge.github.io/IsaacDocs/rep/EntityRef.html) Source, boolean DoScreenEffects = true ) {: .copyable aria-label='Functions' }
将尝试像肉斧道具那样将敌人分裂成两个。如果敌人在分裂前因伤害死亡则返回 `false`，否则返回 `true`。

### TryThrow () {: aria-label='Functions' }
#### boolean TryThrow ( [EntityRef](https://wofsauge.github.io/IsaacDocs/rep/EntityRef.html) Source, [Vector](Vector.md) Direction, float Force ) {: .copyable aria-label='Functions' }
???+ info "信息"
`Force` 仅适用于 NPC 便便（它会被修改，然后用作 V1.y，V1.x 为 -20.0），可能不准确。这需要进一步研究。

### UpdateDirtColor () {: aria-label='Functions' }
#### void UpdateDirtColor ( boolean Immediate ) {: .copyable aria-label='Functions' }
指示实体更新其泥土颜色。在原版实体中，这通常是自动完成的，但到目前为止，模组实体在这方面一直相当受限。
如果设置了 `Immediate`，泥土颜色将被设置为实体下方的确切颜色。否则，它将在多帧的过程中平滑更新。

### V1 {: aria-label='Variables' }
#### [Vector](Vector.md) V1 {: .copyable aria-label='Variables' }
Fix of original function that now correctly returns a pointer to the Vector.
___
### V2 {: aria-label='Variables' }
#### [Vector](Vector.md) V2 {: .copyable aria-label='Variables' }
Fix of original function that now correctly returns a pointer to the Vector.
___
