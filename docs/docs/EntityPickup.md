---
tags:
  - Class
---
# Class "EntityPickup"

## Class Diagram
--8<-- "docs/snippets/EntityClassDiagram_NewFunkyMode.md"
## Functions

### AddCollectibleCycle () {: aria-label='Functions' }
#### boolean AddCollectibleCycle ( int id ) {: .copyable aria-label='Functions' }

___
### CanReroll () {: aria-label='Functions' }
#### boolean CanReroll ( ) {: .copyable aria-label='Functions' }

___
### GetAlternatePedestal () {: aria-label='Functions' }
#### int GetAlternatePedestal ( ) {: .copyable aria-label='Functions' }

___
### GetCollectibleCycle () {: aria-label='Functions' }
#### [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html)[] GetCollectibleCycle ( ) {: .copyable aria-label='Functions' }
返回一个表格，其中包含在其收藏品循环（例如错误王冠）中使用的所有 [CollectibleTypes](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html)。

### GetDropDelay () {: aria-label='Functions' }
#### int GetDropDelay ( ) {: .copyable aria-label='Functions' }

___
### GetLootList () {: aria-label='Functions' }
#### [LootList](LootList.md) GetLootList ( ) {: .copyable aria-label='Functions' }
返回拾取物的 [LootList](LootList.md) 的**只读**版本。可以通过使用嗝屁猫之眼收藏品来查看拾取物中的战利品。

### GetPickupGhost () {: aria-label='Functions' }
#### [EntityEffect](EntityEffect.md) GetPickupGhost ( ) {: .copyable aria-label='Functions' }
返回通过嗝屁猫之眼可见的 `EffectVariant.PICKUP_GHOST` 实体效果。如果不可见，则返回 `nil`。

### GetPriceSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetPriceSprite ( ) {: .copyable aria-label='Functions' }

___
### GetRandomPickupVelocity () {: aria-label='Functions' }
#### [Vector](Vector.md) GetRandomPickupVelocity ( [Vector](Vector.md) Position, [RNG](RNG.md) RNG = nil, int VelocityType = 0 ) {: .copyable aria-label='Functions' }
???+ warning "Warning"
`VelocityType` 1 会将拾取物朝下方的锥形区域射出，主要用于乞丐的奖励。
`VelocityType` 0 会将拾取物朝所需位置周围的随机方向射出。
这是一个静态函数，必须通过 `EntityPickup.GetRandomPickupVelocity(Position, RNG, VelocityType)` 调用。
`VelocityType` 似乎也会影响挑战房间中的拾取物，使其速度更慢。

### GetVarData () {: aria-label='Functions' }
#### int GetVarData ( ) {: .copyable aria-label='Functions' }

___
### IsBlind () {: aria-label='Functions' }
#### boolean IsBlind ( ) {: .copyable aria-label='Functions' }
此值不考虑盲目诅咒，它仅反映通常在不涉及诅咒的情况下处于盲目状态的拾取物的盲目状态。例如：隐藏路线的额外物品。
如果拾取物是收藏品基座且处于隐藏状态，则返回 `true`。对于非收藏品实体拾取物，始终返回 `false`。
???+ warning "Warning"

### MakeShopItem () {: aria-label='Functions' }
#### void MakeShopItem ( int ShopItemID ) {: .copyable aria-label='Functions' }

___
### RemoveCollectibleCycle () {: aria-label='Functions' }
#### void RemoveCollectibleCycle ( ) {: .copyable aria-label='Functions' }

___
### SetAlternatePedestal () {: aria-label='Functions' }
#### void SetAlternatePedestal ( int PedestalType ) {: .copyable aria-label='Functions' }
设置物品基座的图形。对非收藏品实体拾取物无效。

### SetDropDelay () {: aria-label='Functions' }
#### void SetDropDelay ( int Delay ) {: .copyable aria-label='Functions' }

___
### SetForceBlind () {: aria-label='Functions' }
#### void SetForceBlind ( boolean SetBlind ) {: .copyable aria-label='Functions' }
像盲目诅咒一样隐藏基座物品。对非收藏品实体拾取物无效。

### SetNewOptionsPickupIndex () {: aria-label='Functions' }
#### int SetNewOptionsPickupIndex ( ) {: .copyable aria-label='Functions' }
返回新的拾取物索引。

### SetVarData () {: aria-label='Functions' }
#### void SetVarData ( int VarData ) {: .copyable aria-label='Functions' }

___
### TriggerTheresOptionsPickup () {: aria-label='Functions' }
#### void TriggerTheresOptionsPickup ( ) {: .copyable aria-label='Functions' }
移除与目标拾取物具有相同选项组（OptionsPickupIndex）的拾取物。

### TryFlip () {: aria-label='Functions' }
#### boolean TryFlip ( ) {: .copyable aria-label='Functions' }
尝试翻转收藏品，例如在使用翻转物品对带有第二个全息收藏品（位于第一个后面）的收藏品基座进行操作时。如果成功则返回 `true`，否则返回 `false`；如果用于非收藏品实体拾取物，也返回 `false`。

### TryInitOptionCycle () {: aria-label='Functions' }
#### boolean TryInitOptionCycle ( int NumCycle ) {: .copyable aria-label='Functions' }
使收藏品基座开始循环显示指定数量的收藏品，包括其自身的收藏品类型。

### TryRemoveCollectible () {: aria-label='Functions' }
#### boolean TryRemoveCollectible ( ) {: .copyable aria-label='Functions' }
如果成功从基座上移除了一个收藏品，则返回 `true`。如果基座已经为空，或者对非收藏品实体拾取物调用此函数，则返回 `false`。
尝试从物品基座上移除收藏品。

### UpdatePickupGhosts () {: aria-label='Functions' }
#### void UpdatePickupGhosts ( ) {: .copyable aria-label='Functions' }
根据拾取物当前的 [LootList](LootList.md) 更新 `EffectVariant.PICKUP_GHOST` 实体效果。