---
tags:
  - Class
---
# Class "EntityPlayer"

This class contains both new functions and modified reimplementations of existing ones.

## Class Diagram
--8<-- "docs/snippets/EntityClassDiagram_NewFunkyMode.md"
## Modified Functions

### AddCacheFlags () {: aria-label='Modified Functions' }
#### void AddCacheFlags ( [CacheFlag](https://wofsauge.github.io/IsaacDocs/rep/enums/CacheFlag.html) CacheFlag, boolean EvaluateItems = false ) {: .copyable aria-label='Modified Functions' }
现在接受一个可选的布尔值，用于确定在添加缓存标志后是否应自动调用 [EntityPlayer](EntityPlayer.md):EvaluateItems()。在大多数情况下，你可能希望这样做。

### AddCollectibleEffect, () {: aria-label='Modified Functions' }
#### void AddCollectibleEffect ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) ctype, bool applycostume, int cooldown = vanillacd, bool additive = true ) {: .copyable aria-label='Modified Functions' }
Shortcut of TemporaryEffects:AddCollectibleEffect with extra args to handle cooldown. The additive parameter determines if the cooldown should be added to the preexistent cooldown value or if it should be set for that value. You can use negative cooldown values with additive to reduce preexistent cooldown.

___
### AddNullItemEffect, () {: aria-label='Modified Functions' }
#### void AddNullItemEffect ( int nullItemid, bool applycostume, int cooldown = vanillacd, bool additive = true ) {: .copyable aria-label='Modified Functions' }
Shortcut of TemporaryEffects:AddNullItemEffect with extra args to handle cooldown. The additive parameter determines if the cooldown should be added to the preexistent cooldown value or if it should be set for that value. You can use negative cooldown values with additive to reduce preexistent cooldown.

___
### ClearDeadEyeCharge () {: aria-label='Modified Functions' }
#### void ClearDeadEyeCharge ( boolean Force = false ) {: .copyable aria-label='Modified Functions' }
现在接受一个 `Force` 参数，以强制重置充能，而不是仅通过概率来决定是否重置。

### GetCollectibleNum () {: aria-label='Modified Functions' }
#### int GetCollectibleNum ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, boolean OnlyCountTrueItems = false, bool IgnoreSpoof = false ) {: .copyable aria-label='Modified Functions' }
现在接受一个 `IgnoreSpoof` 参数，该参数会忽略固有物品。

### GetMultiShotParams () {: aria-label='Modified Functions' }
#### [MultiShotParams](MultiShotParams.md) GetMultiShotParams ( [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html) WeaponType ) {: .copyable aria-label='Modified Functions' }
现在返回一个合适的 `MultiShotParams` 对象。

### GetMultiShotPositionVelocity () {: aria-label='Modified Functions' }
#### [PosVel](https://wofsauge.github.io/IsaacDocs/rep/PlayerTypes_PosVel.html) GetMultiShotPositionVelocity ( int LoopIndex, [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html) WeaponType, [Vector](Vector.md) ShotDirection, float ShotSpeed, [MultiShotParams](MultiShotParams.md) Params ) {: .copyable aria-label='Modified Functions' }
与原版函数相比，此实现进一步增强，若 LoopIndex 高于 [MultiShotParams:GetNumTears()](MultiShotParams.md#getnumtears) 则会抛出错误。此函数在 1.7.8 之后的某个时间从 API 中消失了。

### GetPocketItem () {: aria-label='Modified Functions' }
#### [PocketItem](PocketItem.md) GetPocketItem ( [PillCardSlot](enums/PillCardSlot.md) Slot ) {: .copyable aria-label='Modified Functions' }
获取指定口袋槽中的卡片/药丸/符文。现在返回一个合适的 `PocketItem` 对象。

### HasCollectible () {: aria-label='Modified Functions' }
#### boolean HasCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, boolean IgnoreModifiers = false, boolean IgnoreSpoof = false ) {: .copyable aria-label='Modified Functions' }
现在接受一个 `IgnoreSpoof` 参数，该参数会忽略固有物品。

### BabySkin {: aria-label='Modified Variables' }
#### [BabySubType](https://wofsauge.github.io/IsaacDocs/rep/enums/BabySubType.html) BabySkin  {: .copyable aria-label='Modified Variables' }
Same as default, but now returns a proper integer value instead of userdata.

___

## Functions

### AddActiveCharge () {: aria-label='Functions' }
#### int AddActiveCharge ( int Charge, [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot, boolean FlashHUD = true, boolean Overcharge = false, boolean Force = false ) {: .copyable aria-label='Functions' }
返回实际添加的充能数量，该数量可能会受到目标物品的最大充能值限制。
???- info "信息"
`FlashHUD` 似乎是多余的。无论使用 `true` 还是 `false`，充能条都会闪烁。

### AddBoneOrbital () {: aria-label='Functions' }
#### void AddBoneOrbital ( [Vector](Vector.md) Position ) {: .copyable aria-label='Functions' }

___
### AddCustomCacheTag () {: aria-label='Functions' }
#### void AddCustomCacheTag ( string OR \{string, string, ...\}, bool EvaluateItems = false ) {: .copyable aria-label='Functions' }
添加自定义缓存标签，以便在下一次运行 EvaluateItems 时进行评估（如果传递了可选布尔值，则立即进行评估）。有关自定义缓存的更多信息，请参阅 [items.xml](xml/items.md)。

### AddInnateCollectible () {: aria-label='Functions' }
#### void AddInnateCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, int Amount = 1 ) {: .copyable aria-label='Functions' }
???+ bug "漏洞"
目前此函数会直接修改 WispCollectiblesList 的内容，因此如果此列表在精灵初始化/删除时更新，或者玩家退出游戏，你添加的固有物品将不会被保存。

### AddLeprosy () {: aria-label='Functions' }
#### void AddLeprosy ( ) {: .copyable aria-label='Functions' }
目前此功能仍然限制最多生成三个跟班，若要更改此限制，需要进一步修改。
???+ info "信息"

### AddLocust () {: aria-label='Functions' }
#### void AddLocust ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, [Vector](Vector.md) Position ) {: .copyable aria-label='Functions' }
- Scorpio
- Mutant Spider
- 120 Volt
- Breakfast (default)
- Brimstone
- Number One
- The Inner Eye
- The Common Cold
- Jacob's Ladder
- Blood of the Martyr
- Halo of Flies
- Spoon Bender
- Ipecac
- Cricket's Head
???- info "支持的物品"
有一些物品会生成独特的蝗虫
- Fire Mind
- Holy Light

### AddSmeltedTrinket () {: aria-label='Functions' }
#### boolean AddSmeltedTrinket ( [TrinketType](https://wofsauge.github.io/IsaacDocs/rep/enums/TrinketType.html) Trinket, boolean FirstTimePickingUp = true ) {: .copyable aria-label='Functions' }
直接将一个吞下的饰品添加到玩家的库存中。如果饰品成功添加，则返回 `true`，否则返回 `false`。

### AddUrnSouls () {: aria-label='Functions' }
#### void AddUrnSouls ( int Count = 0 ) {: .copyable aria-label='Functions' }  

___
### BlockCollectible () {: aria-label='Functions' }
#### void BlockCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }  
阻止提供的 [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html)。这会使游戏认为你没有该物品，即使它在你的库存中。

### CanAddCollectibleToInventory () {: aria-label='Functions' }
#### boolean CanAddCollectibleToInventory ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }

___
### CanCrushRocks () {: aria-label='Functions' }
#### boolean CanCrushRocks ( ) {: .copyable aria-label='Functions' }
- The Nail
???- info "Info"
- Thunder Thighs
- Leo
- Stompy
- Mega Mush
如果玩家拥有以下物品/效果/变身之一，则返回 `true`。

### CanOverrideActiveItem () {: aria-label='Functions' }
#### boolean CanOverrideActiveItem ( [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot ) {: .copyable aria-label='Functions' }

___
### CanUsePill () {: aria-label='Functions' }
#### boolean CanUsePill ( [PillEffect](https://wofsauge.github.io/IsaacDocs/rep/enums/PillEffect.html) ID ) {: .copyable aria-label='Functions' }
根据某些条件（通常与生命值相关），确定玩家是否可以使用给定的药丸效果。

### CheckFamiliarEx () {: aria-label='Functions' }
#### [EntityFamiliar](EntityFamiliar.md)[] CheckFamiliarEx ( int [FamiliarVariant](https://wofsauge.github.io/IsaacDocs/rep/enums/FamiliarVariant.html) Familiar, int TargetCount, [RNG](RNG.md) rng, [ItemConfigItem](ItemConfig_Item.md) SourceItemConfigItem = nil, int FamiliarSubType = -1 ) {: .copyable aria-label='Functions' }
[CheckFamiliar](https://wofsauge.github.io/IsaacDocs/rep/EntityPlayer.html#checkfamiliar) 的一个版本，它会将该函数生成的所有跟班作为一个表返回。

### ClearCollectibleAnim () {: aria-label='Functions' }
#### void ClearCollectibleAnim ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible) {: .copyable aria-label='Functions' }

___
### ClearQueueItem () {: aria-label='Functions' }
#### void ClearQueueItem ( ) {: .copyable aria-label='Functions' }

___
### DropCollectible () {: aria-label='Functions' }
#### void DropCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, [EntityPickup](EntityPickup.md) ExistingPedestal = nil, boolean RemoveFromPlayerForm = false ) {: .copyable aria-label='Functions' }
如果设置了 `ExistingPedestal`，则该基座中包含的收藏品将被替换为掉落的收藏品，而不是生成一个新的基座。

### DropCollectibleByHistoryIndex () {: aria-label='Functions' }
#### [EntityPickup](EntityPickup.md) DropCollectibleByHistoryIndex ( int Idx, [EntityPickup](EntityPickup.md) ExistingPedestal = nil ) {: .copyable aria-label='Functions' }
如果设置了 `ExistingPedestal`，则该基座中包含的收藏品将被替换为掉落的收藏品，而不是生成一个新的基座。

### EnableWeaponType () {: aria-label='Functions' }
#### void EnableWeaponType ( [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html) Weapon, boolean Set ) {: .copyable aria-label='Functions' }

___
### FireBrimstoneBall () {: aria-label='Functions' }
#### [EntityEffect](EntityEffect.md) FireBrimstoneBall ( [Vector](Vector.md) Position, [Vector](Vector.md) Velocity, [Vector](Vector.md) Offset = Vector.Zero ) {: .copyable aria-label='Functions' }
如果玩家拥有科技 X，此函数还会发射一个 [EntityLaser](EntityLaser.md)。激光将以硫磺火球效果为父对象，但不清楚该效果是否也会链接回激光。
???+ info "信息"

### GetActiveItemDesc () {: aria-label='Functions' }
#### [ActiveItemDesc](https://wofsauge.github.io/IsaacDocs/rep/PlayerTypes_ActiveItemDesc.html) GetActiveItemDesc ( [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot = ActiveSlot.SLOT_PRIMARY ) {: .copyable aria-label='Functions' }

___
### GetActiveItemSlot () {: aria-label='Functions' }
#### [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) GetActiveItemSlot ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }

___
### GetActiveMaxCharge () {: aria-label='Functions' }
#### int GetActiveMaxCharge ( [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot ) {: .copyable aria-label='Functions' }

___
### GetActiveMinUsableCharge () {: aria-label='Functions' }
#### int GetActiveMinUsableCharge ( [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot ) {: .copyable aria-label='Functions' }

___
### GetActiveWeaponNumFired () {: aria-label='Functions' }
#### int GetActiveWeaponNumFired ( ) {: .copyable aria-label='Functions' }

___
### GetBagOfCraftingContent () {: aria-label='Functions' }
#### [BagOfCraftingPickup](enums/BagOfCraftingPickup.md)[] GetBagOfCraftingContent ( ) {: .copyable aria-label='Functions' }

___
### GetBagOfCraftingOutput () {: aria-label='Functions' }
#### [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) GetBagOfCraftingOutput ( ) {: .copyable aria-label='Functions' }

___
### GetBagOfCraftingSlot () {: aria-label='Functions' }
#### [BagOfCraftingPickup](enums/BagOfCraftingPickup.md) GetBagOfCraftingSlot ( int SlotID ) {: .copyable aria-label='Functions' }
获取给定 `SlotID` 中合成袋的当前内容。

### GetBladderCharge () {: aria-label='Functions' }
#### int GetBladderCharge ( ) {: .copyable aria-label='Functions' }
返回玩家停止射击并为肾结石物品充能时的当前充能值。

### GetBloodLustCounter () {: aria-label='Functions' }
#### int GetBloodLustCounter ( ) {: .copyable aria-label='Functions' }

___
### GetBodyMoveDirection () {: aria-label='Functions' }
#### [Vector](Vector.md) GetBodyMoveDirection ( ) {: .copyable aria-label='Functions' }

___
### GetBombPlaceDelay () {: aria-label='Functions' }
#### int GetBombPlaceDelay ( ) {: .copyable aria-label='Functions' }
默认炸弹放置延迟为 `30 帧`。

### GetCambionConceptionState () {: aria-label='Functions' }
#### int GetCambionConceptionState ( ) {: .copyable aria-label='Functions' }
返回玩家使用恶魔受胎物品受到伤害的次数。

### GetCambionPregnancyLevel () {: aria-label='Functions' }
#### int GetCambionPregnancyLevel ( ) {: .copyable aria-label='Functions' }
对应恶魔受胎服装的当前可见状态（0 - 2）。

### GetCollectiblesList () {: aria-label='Functions' }
#### table GetCollectiblesList ( ) {: .copyable aria-label='Functions' }
返回一个表，其中包含玩家拥有的每个收藏品的数量，不计算固有物品。
???- example "示例代码"
这段代码打印玩家拥有的悲伤洋葱的数量
```lua
local collectiblesList = player:GetCollectiblesList()
print(collectiblesList[CollectibleType.COLLECTIBLE_SAD_ONION])
```

### GetConceptionFamiliarFlags () {: aria-label='Functions' }
#### int GetConceptionFamiliarFlags ( ) {: .copyable aria-label='Functions' }
返回一个位掩码，对应由圣灵受胎 / 恶魔受胎生成的跟班。此位掩码提供的额外跟班在跟班缓存评估期间生成，但仅当玩家拥有这两个物品之一时才会生成.

### GetCostumeLayerMap () {: aria-label='Functions' }
#### table GetCostumeLayerMap ( ) {: .copyable aria-label='Functions' }
返回玩家服装精灵层数据的表格，包含以下字段：
| Field | Type | Comment |
| :-- | :-- | :-- |
| costumeIndex | int | 该层活跃/可见服装的索引。若该层无服装，值为 `-1`. |
| priority | int | 对应动画文件（anm2）的精灵层 ID。若该层无服装，值为 `-1`. |
| layerID | int | 服装在 `costumes2.xml` 中列出的优先级。若该层无服装，值为 `-1` |
| isBodyLayer | boolean | 若服装是身体服装则为 `true` ，否则（包括该层无服装时）为 `false`. |
???- info "More Layer Map Info"
返回表格的索引顺序与 `PlayerSpriteLayer` 对应。但由于 Lua 和 C++ 数组起始索引的差异，`CostumeLayerMap` 的索引需减 1 ，且其 `costumeIndex` 需加 1 才能获取准确信息

下方代码片段用于显示所有当前已占用的服装层，打印内容格式为：`PlayerSpriteLayer - 层名称 - 物品名称/NullItemID - Anm2 文件路径` 
???+ example "Example Code"
```lua
    local player = Isaac.GetPlayer()
    local map = Isaac.GetPlayer():GetCostumeLayerMap()
    print("-------------------------------------------------------------------")
    local costumeSpriteDescs = player:GetCostumeSpriteDescs()
    for layer, mapData in ipairs(map) do
        if mapData.costumeIndex == -1 then goto continue end
        local costumeSpriteDesc = costumeSpriteDescs[mapData.costumeIndex + 1]
        local sprite = costumeSpriteDesc:GetSprite()
        local itemConfig = costumeSpriteDesc:GetItemConfig()
        local layerName = sprite:GetLayer(mapData.layerID):GetName()
        local costumeName = itemConfig.Name ~= "" and Isaac.GetString("Items", itemConfig.Name) or "NullItemID "..itemConfig.ID
        local spritePath = sprite:GetFilename()
        print(layer - 1, "-", layerName, "-", costumeName, "-", spritePath)
        ::continue::
    end
    print("-------------------------------------------------------------------")
```

### GetCostumeSpriteDescs () {: aria-label='Functions' }
#### [CostumeSpriteDesc](CostumeSpriteDesc.md)[] GetCostumeSpriteDescs ( ) {: .copyable aria-label='Functions' }
返回一个 [CostumeSpriteDesc](CostumeSpriteDesc.md) 类型的表。

### GetCustomCacheValue () {: aria-label='Functions' }
#### float GetCustomCacheValue ( string CustomCacheTag ) {: .copyable aria-label='Functions' }
返回指定自定义缓存标签的当前缓存值。如果提供的标签尚未评估，则默认返回 `0`。
有关自定义缓存的更多信息，请参阅 [items.xml](xml/items.md)。

### GetD8DamageModifier () {: aria-label='Functions' }
#### int GetD8DamageModifier ( ) {: .copyable aria-label='Functions' }

___
### GetD8FireDelayModifier () {: aria-label='Functions' }
#### int GetD8FireDelayModifier ( ) {: .copyable aria-label='Functions' }

___
### GetD8RangeModifier () {: aria-label='Functions' }
#### int GetD8RangeModifier ( ) {: .copyable aria-label='Functions' }

___
### GetD8SpeedModifier () {: aria-label='Functions' }
#### int GetD8SpeedModifier ( ) {: .copyable aria-label='Functions' }

___
### GetDamageModifier () {: aria-label='Functions' }
#### int GetDamageModifier ( ) {: .copyable aria-label='Functions' }
该修饰符以固定伤害的形式应用于玩家。
“实验性治疗” 根据随机生成的伤害值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### GetDeadEyeCharge () {: aria-label='Functions' }
#### int GetDeadEyeCharge ( ) {: .copyable aria-label='Functions' }

___
### GetDeathAnimName () {: aria-label='Functions' }
#### string GetDeathAnimName ( ) {: .copyable aria-label='Functions' }
- `LostDeath` - 当玩家扮演 “迷失者”、处于 “迷失者诅咒” 状态、扮演 “遗忘者之魂” 或处于 “堕落雅各布的幽灵形态” 时。
返回玩家死亡动画的名称。
可能返回以下字符串：
- `Death` - 常规死亡动画名称。
???+ info "返回信息"

### GetEdenDamage () {: aria-label='Functions' }
#### float GetEdenDamage ( ) {: .copyable aria-label='Functions' }
返回玩家伊甸随机属性中伤害属性的偏移量。

### GetEdenFireDelay () {: aria-label='Functions' }
#### float GetEdenFireDelay ( ) {: .copyable aria-label='Functions' }
返回玩家伊甸随机属性中射击延迟属性的偏移量。

### GetEdenLuck () {: aria-label='Functions' }
#### float GetEdenLuck ( ) {: .copyable aria-label='Functions' }
返回玩家伊甸随机属性中幸运属性的偏移量。

### GetEdenRange () {: aria-label='Functions' }
#### float GetEdenRange ( ) {: .copyable aria-label='Functions' }
返回玩家伊甸随机属性中射程属性的偏移量。

### GetEdenShotSpeed () {: aria-label='Functions' }
#### float GetEdenShotSpeed ( ) {: .copyable aria-label='Functions' }
返回玩家伊甸随机属性中射击速度属性的偏移量。

### GetEdenSpeed () {: aria-label='Functions' }
#### float GetEdenSpeed ( ) {: .copyable aria-label='Functions' }
返回玩家伊甸随机属性中移动速度属性的偏移量。

### GetEnterPosition () {: aria-label='Functions' }
#### [Vector](Vector.md) GetEnterPosition ( ) {: .copyable aria-label='Functions' }        

___
### GetEntityConfigPlayer () {: aria-label='Functions' }
#### [EntityConfigPlayer](EntityConfigPlayer.md) GetEntityConfigPlayer ( ) {: .copyable aria-label='Functions' }

___
### GetEpiphoraCharge () {: aria-label='Functions' }
#### int GetEpiphoraCharge ( ) {: .copyable aria-label='Functions' }

___
### GetEveSumptoriumCharge () {: aria-label='Functions' }
#### int GetEveSumptoriumCharge ( ) {: .copyable aria-label='Functions' }
返回 “堕落夏娃” 固有 “吸食器” 能力的当前充能值。

### GetFireDelayModifier () {: aria-label='Functions' }
#### int GetFireDelayModifier ( ) {: .copyable aria-label='Functions' }
“实验性治疗” 根据随机生成的射击延迟值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
为玩家提供 `0.5 * 修饰符` 的固定每秒眼泪数。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### GetFlippedForm () {: aria-label='Functions' }
#### [EntityPlayer](EntityPlayer.md) GetFlippedForm ( ) {: .copyable aria-label='Functions' }
返回当前角色的翻转形态（仅适用于 “堕落拉撒路”）。
否则返回 `nil`。

### GetFocusEntity () {: aria-label='Functions' }
#### [Entity](Entity.md) GetFocusEntity ( ) {: .copyable aria-label='Functions' }
返回活动相机用于确定相机焦点的实体。这可以是 [标记](https://bindingofisaacrebirth.fandom.com/wiki/Marked) 目标 [EntityEffect](EntityEffect.md) 或武器实体。
如果这些都不存在，则返回 `nil`。

### GetFootprintColor () {: aria-label='Functions' }
#### [KColor](https://wofsauge.github.io/IsaacDocs/rep/KColor.html) GetFootprintColor ( boolean LeftFootprint ) {: .copyable aria-label='Functions' }

___
### GetGlitchBabySubType () {: aria-label='Functions' }
#### int GetGlitchBabySubType ( ) {: .copyable aria-label='Functions' }

___
### GetGlyphOfBalanceDrop () {: aria-label='Functions' }
#### table GetGlyphOfBalanceDrop ( int Variant = -1, int SubType = -1 ) {: .copyable aria-label='Functions' }
返回一个表，其中包含可能掉落的 [平衡符文](https://bindingofisaacrebirth.fandom.com/wiki/Glyph_of_Balance) 的变体和子类型。

### GetGnawedLeafTimer () {: aria-label='Functions' }
#### int GetGnawedLeafTimer ( ) {: .copyable aria-label='Functions' }

___
### GetGreedsGulletHearts () {: aria-label='Functions' }
#### int GetGreedsGulletHearts ( ) {: .copyable aria-label='Functions' }

___
### GetHallowedGroundCountdown () {: aria-label='Functions' }
#### int GetHallowedGroundCountdown ( ) {: .copyable aria-label='Functions' }
返回玩家从 “神圣之地/伯利恒之星” 光环中保留属性的宽限期倒计时。

### GetHeadDirectionLockTime () {: aria-label='Functions' }
#### int GetHeadDirectionLockTime ( ) {: .copyable aria-label='Functions' }
玩家头部应强制保持当前方向的时长。`-1`（或更低）表示当前方向未被锁定。

### GetHealthType () {: aria-label='Functions' }
#### [HealthType](enums/HealthType.md) GetHealthType ( ) {: .copyable aria-label='Functions' }

___
### GetHeldEntity () {: aria-label='Functions' }
#### [Entity](Entity.md) GetHeldEntity ( ) {: .copyable aria-label='Functions' }
如果玩家当前没有手持实体，则返回 `nil`。
返回玩家举在头顶的实体，例如可投掷的红色炸弹或 [抱摔！](https://bindingofisaacrebirth.fandom.com/wiki/Suplex!)。

### GetHeldSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetHeldSprite ( ) {: .copyable aria-label='Functions' }
获取玩家进行涉及将精灵举在头顶的动画时使用的 [Sprite](Sprite.md) 对象，例如使用主动道具时。

### GetHistory () {: aria-label='Functions' }
#### [History](History.md) GetHistory ( ) {: .copyable aria-label='Functions' }

___
### GetImmaculateConceptionState () {: aria-label='Functions' }
#### int GetImmaculateConceptionState ( ) {: .copyable aria-label='Functions' }
返回玩家使用 “圣灵受胎” 道具收集到的红心数量。在生成跟班/魂心后重置为 0。

### GetKeepersSackBonus () {: aria-label='Functions' }
#### int GetKeepersSackBonus ( ) {: .copyable aria-label='Functions' }
获取玩家持有 [“守护者之袋”](https://bindingofisaacrebirth.fandom.com/wiki/Keeper's_Sack) 时花费的硬币数量。

### GetLaserColor () {: aria-label='Functions' }
#### [Color](Color.md) GetLaserColor ( ) {: .copyable aria-label='Functions' }

___
### GetLuckModifier () {: aria-label='Functions' }
#### int GetLuckModifier ( ) {: .copyable aria-label='Functions' }
“实验性治疗” 根据随机生成的幸运值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
该修饰符直接添加到玩家的幸运属性上。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### GetMaggySwingCooldown () {: aria-label='Functions' }
#### int GetMaggySwingCooldown ( ) {: .copyable aria-label='Functions' }
返回 “堕落抹大拉” 受到伤害后挥击攻击的冷却剩余帧数。如果玩家不是 “堕落抹大拉”，则返回 `0`。

### GetMarkedTarget () {: aria-label='Functions' }
#### [EntityEffect](https://wofsauge.github.io/IsaacDocs/rep/EntityEffect.html) GetMarkedTarget ( ) { : .copyable aria-label='Functions' }
如果目标未显示在地面上，此函数返回 `nil`。
返回代表 [标记](https://bindingofisaacrebirth.fandom.com/wiki/Marked) 道具目标的实体效果。

### GetMaxBladderCharge () {: aria-label='Functions' }
#### int GetMaxBladderCharge ( ) {: .copyable aria-label='Functions' }
返回玩家停止射击并为 “肾结石” 道具充能时的最大充能值。

### GetMaxBombs () {: aria-label='Functions' }
#### int GetMaxBombs ( ) {: .copyable aria-label='Functions' }
返回玩家当前可持有的最大炸弹数量。

### GetMaxCoins () {: aria-label='Functions' }
#### int GetMaxCoins ( ) {: .copyable aria-label='Functions' }
返回玩家当前可持有的最大硬币数量。

### GetMaxKeys () {: aria-label='Functions' }
#### int GetMaxKeys ( ) {: .copyable aria-label='Functions' }
返回玩家当前可持有的最大钥匙数量。

### GetMaxPeeBurstCooldown () {: aria-label='Functions' }
#### int GetMaxPeeBurstCooldown ( ) {: .copyable aria-label='Functions' }
返回 “肾结石” 道具的最大攻击持续时间。

### GetMaxPocketItems () {: aria-label='Functions' }
#### int GetMaxPocketItems ( ) {: .copyable aria-label='Functions' }

___
### GetMegaBlastDuration () {: aria-label='Functions' }
#### int GetMegaBlastDuration ( ) {: .copyable aria-label='Functions' }

___
### GetMetronomeCollectibleID () {: aria-label='Functions' }
#### int GetMetronomeCollectibleID ( ) {: .copyable aria-label='Functions' }

___
### GetMovingBoxContents () {: aria-label='Functions' }
#### [EntitiesSaveStateVector](EntitiesSaveStateVector.md) GetMovingBoxContents ( ) {: .copyable aria-label='Functions' }
返回玩家通过 “移动箱” 道具存储的拾取物。

### GetNextUrethraBlockFrame () {: aria-label='Functions' }
#### int GetNextUrethraBlockFrame ( ) {: .copyable aria-label='Functions' }
返回玩家停止射击并开始为 [“肾结石”](https://bindingofisaacrebirth.fandom.com/wiki/Kidney_Stone) 道具充能的帧数。

### GetPeeBurstCooldown () {: aria-label='Functions' }
#### int GetPeeBurstCooldown ( ) {: .copyable aria-label='Functions' }
返回 [“肾结石”](https://bindingofisaacrebirth.fandom.com/wiki/Kidney_Stone) 道具的攻击持续时间。

### GetPlayerFormCounter () {: aria-label='Functions' }
#### int GetPlayerFormCounter ( [PlayerForm](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerForm.html) PlayerFormID ) {: .copyable aria-label='Functions' } 
返回玩家与指定变身相关联的道具数量。

### GetPlayerIndex () {: aria-label='Functions' }
#### int GetPlayerIndex ( ) {: .copyable aria-label='Functions' }

___
### GetPonyCharge () {: aria-label='Functions' }
#### int GetPonyCharge ( ) {: .copyable aria-label='Functions' }
返回 “一匹小马” 或 “白色小马” 道具充能效果停用前的剩余帧数。

### GetPurityState () {: aria-label='Functions' }
#### [PurityState](enums/PurityState.md) GetPurityState ( ) {: .copyable aria-label='Functions' }
返回 [“纯洁”](https://bindingofisaacrebirth.fandom.com/wiki/Purity) 道具效果的当前状态。如果玩家没有 “纯洁” 道具，则返回 `PurityState.BLUE`。

### GetRedStewBonusDuration () {: aria-label='Functions' }
#### int GetRedStewBonusDuration ( ) {: .copyable aria-label='Functions' }
返回 “红炖菜” 道具伤害加成效果的剩余帧数。

### GetShotSpeedModifier () {: aria-label='Functions' }
#### int GetShotSpeedModifier ( ) {: .copyable aria-label='Functions' }
“实验性治疗” 根据随机生成的射击速度值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
为玩家的射击速度增加 `0.2 * 修饰符`。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### GetSmeltedTrinkets () {: aria-label='Functions' }
#### table GetSmeltedTrinkets ( ) {: .copyable aria-label='Functions' }
返回一个包含熔炼饰品及其对应数量的表。返回的表包含以下字段：
|:--|:--|:--|
|字段|类型|说明|
| goldenTrinketAmount | int | |
| trinketAmount | int | |

### GetSpecialGridCollision () {: aria-label='Functions' }
#### int GetSpecialGridCollision ( [Vector](Vector.md) Position = self.Position ) {: .copyable aria-label='Functions' }      

___
### GetSpeedModifier () {: aria-label='Functions' }
#### int GetSpeedModifier ( ) {: .copyable aria-label='Functions' }
为玩家的移动速度增加 `0.2 * 修饰符`。
“实验性治疗” 根据随机生成的移动速度值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### GetSpoofedCollectiblesList () {: aria-label='Functions' }
#### table[] GetSpoofedCollectiblesList ( ) {: .copyable aria-label='Functions' }
| 是否被阻挡 | boolean | |
| 道具 ID | [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) | |
|:--|:--|:--|
|字段|类型|说明|
| 追加数量 | int | |

### GetTearDisplacement () {: aria-label='Functions' }
#### int GetTearDisplacement ( ) {: .copyable aria-label='Functions' }
- `1` 右眼
???+ info "返回信息"
- `-1` 左眼
返回玩家的眼泪偏移值，用于检查玩家从哪只眼睛射击。

### GetTotalActiveCharge () {: aria-label='Functions' }
#### int GetTotalActiveCharge ( [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot ) {: .copyable aria-label='Functions' }

___
### GetUrnSouls () {: aria-label='Functions' }
#### int GetUrnSouls ( ) {: .copyable aria-label='Functions' }

___
### GetVoidedCollectiblesList () {: aria-label='Functions' }
#### [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html)[] GetVoidedCollectiblesList ( ) {: .copyable aria-label='Functions' }
返回一个包含所有被 “虚空” 道具吞噬的主动道具 [CollectibleTypes](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) 的表。

### GetWeapon () {: aria-label='Functions' }
#### [Weapon](Weapon.md) GetWeapon ( int Slot ) {: .copyable aria-label='Functions' }
???- info "信息"
始终检查是否为 `nil`，即使是插槽 `1`，因为它可以被模组通过 [Isaac.DestroyWeapon()](Isaac.md#destroyweapon) 删除。
- `4` - 额外武器。
武器插槽及其说明：
返回相应插槽中的武器对象，如果未找到武器则返回 `nil`。插槽编号必须在 `0` 到 `4` 之间。
- `2` - 额外武器。原版游戏中很少有这种情况，但模组可以填充此插槽。
- `1` - 主武器。
- `3` - 额外武器。
- `0` - 备用武器，如 “缺口斧” 和 “灵魂瓮”。

### GetWeaponModifiers () {: aria-label='Functions' }
#### int GetWeaponModifiers ( ) {: .copyable aria-label='Functions' }
返回一个 [WeaponModifiers](enums/WeaponModifier.md) 类型的位掩码。

### GetWildCardItem () {: aria-label='Functions' }
#### int GetWildCardItem ( ) {: .copyable aria-label='Functions' }
如果玩家使用了主动道具，则返回其 `CollectibleType`。如果玩家使用了消耗品，则返回其变体。如果玩家使用了 “问号卡”，则返回 `1`。如果玩家之前从未使用过主动道具，则返回 `0`。
返回玩家最后使用的道具，再次使用 “万能卡” 时将激活该道具。

### GetWildCardItemType () {: aria-label='Functions' }
#### [PocketItemType](enums/PocketItemType.md) GetWildCardItemType ( ) {: .copyable aria-label='Functions' }
返回玩家最后使用的道具类型，再次使用 “万能卡” 时将激活该道具。
如果玩家使用了消耗品（包括 “问号卡”），则返回 `ItemType.ITEM_PASSIVE`。如果玩家之前从未使用过主动道具，则返回 `255`。

### GetWispCollectiblesList () {: aria-label='Functions' }
#### table GetWispCollectiblesList ( ) {: .copyable aria-label='Functions' }
返回一个与玩家拥有的道具幽灵对应的 [CollectibleTypes](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) 表。

### HasChanceRevive () {: aria-label='Functions' }
#### boolean HasChanceRevive ( ) {: .copyable aria-label='Functions' }
如果玩家的额外生命计数上会显示 “?”，则返回 true（即玩家拥有 “古比项圈”，或在 REPENTOGON 的 [自定义标签 items.xml 属性](xml/items.md) 中有 `chancerevive` 字符串的模组复活道具）。

### HasGoldenTrinket () {: aria-label='Functions' }
#### boolean HasGoldenTrinket ( [TrinketType](https://wofsauge.github.io/IsaacDocs/rep/enums/TrinketType.html) Trinket ) {: .copyable aria-label='Functions' }
如果玩家拥有指定 [TrinketType](https://wofsauge.github.io/IsaacDocs/rep/enums/TrinketType.html) 的金色变体，则返回 true。

### HasInstantDeathCurse () {: aria-label='Functions' }
#### boolean HasInstantDeathCurse ( ) {: .copyable aria-label='Functions' }
当玩家处于由下水道的白色火焰或 “迷失者之魂” 触发的 “迷失者” 形态时（或在 “堕落雅各布” 的幽灵形态下被 “黑暗以扫” 触摸时），返回 true。

### HasPoisonImmunity () {: aria-label='Functions' }
#### boolean HasPoisonImmunity ( ) {: .copyable aria-label='Functions' }

___
### IncrementPlayerFormCounter () {: aria-label='Functions' }
#### void IncrementPlayerFormCounter ( [PlayerForm](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerForm.html) Form, int Count ) {: .copyable aria-label='Functions' }
增加或减少玩家向某一变身的计数器。`Count` 可以为负数，以减少 [PlayerForm](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerForm.html)。

### InitPostLevelInitStats () {: aria-label='Functions' }
#### void InitPostLevelInitStats ( ) {: .copyable aria-label='Functions' }
在使用 `InitTwin` 生成具有 “特殊” 眼泪的角色（如 “遗忘者”、“莉莉丝”、“阿撒兹勒” 等）后调用此函数，否则他们将不会拥有正确的眼泪类型。

### InitTwin () {: aria-label='Functions' }
#### [EntityPlayer](EntityPlayer.md) InitTwin ( [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) PlayerType ) {: .copyable aria-label='Functions' }
初始化一个由玩家同一控制器控制的新玩家。
???+ bug "Bug"
我们已从 \_Kilburn 处确认，这在原版角色中是硬编码处理的。我们需要为此添加一个解决方案。
双胞胎玩家在保存并继续游戏时会与其主双胞胎不同步。这会在单人游戏中导致软锁，因为游戏会提示连接控制器。

### IsCollectibleAnimFinished () {: aria-label='Functions' }
#### boolean IsCollectibleAnimFinished ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, string Animation ) {: .copyable aria-label='Functions' }
如果与道具关联的动画可见，则返回 true。

### IsCollectibleBlocked () {: aria-label='Functions' }
#### boolean IsCollectibleBlocked ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
如果 [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) 被阻挡，则返回 true。道具只能通过 [BlockCollectible](EntityPlayer.md#blockcollectible) 函数阻挡。

### IsCollectibleCostumeVisible () {: aria-label='Functions' }
#### boolean IsCollectibleCostumeVisible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, int PlayerSpriteLayerID ) {: .copyable aria-label='Functions' }
如果与道具关联的服装可见，则返回 `true`。

### IsEntityValidTarget () {: aria-label='Functions' }
#### boolean IsEntityValidTarget ( [Entity](Entity.md) Entity ) {: .copyable aria-label='Functions' }

___
### IsFootstepFrame () {: aria-label='Functions' }
#### boolean IsFootstepFrame ( int Foot = -1 ) {: .copyable aria-label='Functions' }       
- `0` - 每 24 帧返回 true。
???+ info "信息"
- `1` - 始终为 false。
- `-1` - 每 12 帧返回 true。

### IsHeadless () {: aria-label='Functions' }
#### boolean IsHeadless ( ) {: .copyable aria-label='Functions' }
如果玩家因 “断头台”、“入侵者”、“剪刀” 和 “斩首攻击” 等道具而无头，则返回 `true`。

### IsHologram () {: aria-label='Functions' }
#### boolean IsHologram ( ) {: .copyable aria-label='Functions' }
如果玩家是拥有 “诞生之权” 的 “堕落拉撒路” 的非激活形态，则返回 `true`。

### IsInvisible () {: aria-label='Functions' }
#### boolean IsInvisible ( ) {: .copyable aria-label='Functions' }
如果玩家拥有 “褪色宝丽来/迷彩内裤” 效果，则返回 `true`。

### IsItemCostumeVisible () {: aria-label='Functions' }
#### boolean IsItemCostumeVisible ( [ItemConfig_Item](ItemConfig_Item.md) Item, int PlayerSpriteLayerID ) {: .copyable aria-label='Functions' }
#### boolean IsItemCostumeVisible ( [ItemConfig_Item](ItemConfig_Item.md) Item, int PlayerSpriteLayerName ) {: .copyable aria-label='Functions' }

___
### IsLocalPlayer () {: aria-label='Functions' }
#### boolean IsLocalPlayer ( ) {: .copyable aria-label='Functions' }
用于在线游戏。如果是本地玩家，则返回 `true`，否则返回 `false`。

### IsNullItemCostumeVisible () {: aria-label='Functions' }
#### boolean IsNullItemCostumeVisible ( int nullItem, int layerID = 0 ) {: .copyable aria-label='Functions' }
#### boolean IsNullItemCostumeVisible ( int nullItem, string layerName ) {: .copyable aria-label='Functions' }

___
### IsPacifist () {: aria-label='Functions' }
#### boolean IsPacifist ( ) {: .copyable aria-label='Functions' }

___
### IsUrethraBlocked () {: aria-label='Functions' }
#### boolean IsUrethraBlocked ( ) {: .copyable aria-label='Functions' }
当玩家因为 [“肾结石”](https://bindingofisaacrebirth.fandom.com/wiki/Kidney_Stone) 道具充能而无法射击时，返回 true。

### MorphToCoopGhost () {: aria-label='Functions' }
#### void MorphToCoopGhost ( ) {: .copyable aria-label='Functions' }
将玩家转变为合作幽灵。

### PlayCollectibleAnim () {: aria-label='Functions' }
#### void PlayCollectibleAnim ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, boolean CheckBodyLayers, string AnimationName, int Frame = -1 ) {: .copyable aria-label='Functions' }
播放与提供的道具关联的动画。

### PlayDelayedSFX () {: aria-label='Functions' }
#### void PlayDelayedSFX ( [SoundEffect](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) ID, int SoundDelay = 0, int FrameDelay = 2, float Volume = 1.0 ) {: .copyable aria-label='Functions' }
延迟播放音效。

### RemoveCollectibleByHistoryIndex () {: aria-label='Functions' }
#### void RemoveCollectibleByHistoryIndex ( int Index ) {: .copyable aria-label='Functions' }
从玩家处移除与指定历史索引关联的道具。

### RemovePocketItem () {: aria-label='Functions' }
#### void RemovePocketItem ( [PillCardSlot](enums/PillCardSlot.md) Slot ) {: .copyable aria-label='Functions' }

___
### RemovePoopSpell () {: aria-label='Functions' }
#### void RemovePoopSpell ( int Position = 0 ) {: .copyable aria-label='Functions' }
从指定队列位置移除便便法术，并将其后的所有法术向前移动以填充空位。最后一个位置将随机选择一个新法术填充。便便法术仅由 “堕落？？？” 使用。

### RerollAllCollectibles () {: aria-label='Functions' }
#### void RerollAllCollectibles ( [RNG](RNG.md) rng, boolean includeActiveItems ) {: .copyable aria-label='Functions' }
重新随机玩家的所有道具。

### ResetPlayer () {: aria-label='Functions' }
#### void ResetPlayer ( ) {: .copyable aria-label='Functions' }
此函数由 “创世纪” 主动道具使用。
???+ info "信息"

### ReviveCoopGhost () {: aria-label='Functions' }
#### boolean ReviveCoopGhost ( ) {: .copyable aria-label='Functions' }

___
### SalvageCollectible () {: aria-label='Functions' }
#### void SalvageCollectible ( [EntityPickup](EntityPickup.md) Pickup, [RNG](RNG.md) rng = PickupDropRNG, [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) Pool = ItemPoolType.POOL_NULL) {: .copyable aria-label='Functions' }
此函数将移除提供的 [EntityPickup](EntityPickup.md)。可以使用覆盖参数避免这种情况。
???+ info "信息"
产生随机数量的各种拾取物，类似于 “堕落该隐” 的能力。

### SetActiveVarData () {: aria-label='Functions' }
#### void SetActiveVarData ( int VarData, [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot ) {: .copyable aria-label='Functions' }

___
### SetBagOfCraftingContent () {: aria-label='Functions' }
#### void SetBagOfCraftingContent ( [BagOfCraftingPickup](enums/BagOfCraftingPickup.md)[] ContentTable ) {: .copyable aria-label='Functions' }
将合成袋的内容设置为表中的内容。表必须使用有效的 [BagOfCraftingPickup](enums/BagOfCraftingPickup.md) ID。表可以短于 8，此时剩余索引将设置为空。

### SetBagOfCraftingOutput () {: aria-label='Functions' }
#### void SetBagOfCraftingOutput ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
将玩家合成袋的输出设置为指定道具。

### SetBagOfCraftingSlot () {: aria-label='Functions' }
#### void SetBagOfCraftingSlot ( int SlotID, [BagOfCraftingPickup](enums/BagOfCraftingPickup.md) PickupID ) {: .copyable aria-label='Functions' }
将玩家合成袋的指定插槽设置为指定拾取物。

### SetBlackHeart () {: aria-label='Functions' }
#### void SetBlackHeart ( int BlackHeart ) {: .copyable aria-label='Functions' }

___
### SetBladderCharge () {: aria-label='Functions' }
#### void SetBladderCharge ( int Charge ) {: .copyable aria-label='Functions' }
由 [“肾结石”](https://bindingofisaacrebirth.fandom.com/wiki/Kidney_Stone) 道具使用。
???+ bug "Bug"
如果在没有 “肾结石” 道具的情况下使用此函数，玩家的头部会变黑。

### SetBloodLustCounter () {: aria-label='Functions' }
#### void SetBloodLustCounter ( int Counter ) {: .copyable aria-label='Functions' }

___
### SetBombPlaceDelay () {: aria-label='Functions' }
#### void SetBombPlaceDelay ( int Delay ) {: .copyable aria-label='Functions' }

___
### SetCambionConceptionState () {: aria-label='Functions' }
#### void SetCambionConceptionState ( int State ) {: .copyable aria-label='Functions' }
请注意，游戏仅在玩家受到伤害且此计数器达到 15、30、60 或 90 时才会生成跟班。你不能直接使用此函数触发诞生。
设置玩家使用 “恶魔受胎” 道具受到的伤害量。

### SetCanShoot () {: aria-label='Functions' }
#### boolean SetCanShoot ( boolean CanShoot ) {: .copyable aria-label='Functions' }
立即禁用（或启用）玩家的射击能力。基础游戏主要在特殊挑战中使用此功能。

### SetConceptionFamiliarFlags () {: aria-label='Functions' }
#### void SetConceptionFamiliarFlags ( [ConceptionFamiliarFlag](enums/ConceptionFamiliarFlag.md) Flags ) {: .copyable aria-label='Functions' }
设置与 “恶魔受胎/圣灵受胎” 生成的跟班对应的位掩码。此位掩码提供的额外跟班在跟班缓存评估期间生成，但仅当玩家拥有这两个道具之一时才会生成。

### SetControllerIndex () {: aria-label='Functions' }
#### void SetControllerIndex ( int Idx ) {: .copyable aria-label='Functions' }        
更改玩家的控制器索引。

### SetDamageModifier () {: aria-label='Functions' }
#### void SetDamageModifier ( int Modifier ) {: .copyable aria-label='Functions' }
该修饰符以固定伤害的形式应用于玩家。
“实验性治疗” 根据随机生成的伤害值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### SetEdenDamage () {: aria-label='Functions' }
#### void SetEdenDamage ( float Value ) {: .copyable aria-label='Functions' }
设置玩家伊甸随机属性中伤害属性的偏移量。对非伊甸或堕落伊甸的玩家无效。

### SetEdenFireDelay () {: aria-label='Functions' }
#### void SetEdenFireDelay ( float Value ) {: .copyable aria-label='Functions' }
设置玩家伊甸随机属性中射击延迟属性的偏移量。对非伊甸或堕落伊甸的玩家无效。

### SetEdenLuck () {: aria-label='Functions' }
#### void SetEdenLuck ( float Value ) {: .copyable aria-label='Functions' }
设置玩家伊甸随机属性中幸运属性的偏移量。对非伊甸或堕落伊甸的玩家无效。

### SetEdenRange () {: aria-label='Functions' }
#### void SetEdenRange ( float Value ) {: .copyable aria-label='Functions' }
设置玩家伊甸随机属性中射程属性的偏移量。对非伊甸或堕落伊甸的玩家无效。

### SetEdenShotSpeed () {: aria-label='Functions' }
#### void SetEdenShotSpeed ( float Value ) {: .copyable aria-label='Functions' }
设置玩家伊甸随机属性中射击速度属性的偏移量。对非伊甸或堕落伊甸的玩家无效。

### SetEdenSpeed () {: aria-label='Functions' }
#### void SetEdenSpeed ( float Value ) {: .copyable aria-label='Functions' }
设置玩家伊甸随机属性中移动速度属性的偏移量。对非伊甸或堕落伊甸的玩家无效。

### SetEveSumptoriumCharge () {: aria-label='Functions' }
#### void SetEveSumptoriumCharge ( int ChargeNum ) {: .copyable aria-label='Functions' }
设置 “堕落夏娃” 固有 “吸食器” 能力的当前充能值。

### SetFireDelayModifier () {: aria-label='Functions' }
#### void SetFireDelayModifier ( int Modifier ) {: .copyable aria-label='Functions' }
“实验性治疗” 根据随机生成的射击延迟值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
为玩家提供 `0.5 * 修饰符` 的固定每秒眼泪数。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### SetFootprintColor () {: aria-label='Functions' }
#### void SetFootprintColor ( [KColor](https://wofsauge.github.io/IsaacDocs/rep/KColor.html) color, boolean RightFoot = false ) {: .copyable aria-label='Functions' }
设置玩家的脚印颜色。
???+ bug "Bug"
此函数目前会导致游戏崩溃 - 将在未来更新中修复。

### SetGnawedLeafTimer () {: aria-label='Functions' }
#### void SetGnawedLeafTimer ( int Timer ) {: .copyable aria-label='Functions' }

___
### SetHallowedGroundCountdown () {: aria-label='Functions' }
#### void SetHallowedGroundCountdown ( int Countdown ) {: .copyable aria-label='Functions' }
设置玩家从 “神圣之地/伯利恒之星” 光环中保留属性的宽限期倒计时。

### SetHeadDirection () {: aria-label='Functions' }
#### void SetHeadDirection ( [Direction](https://wofsauge.github.io/IsaacDocs/rep/enums/Direction.html) Direction, int Time, boolean Force = false ) {: .copyable aria-label='Functions' }
将玩家的头部动画锁定到指定的 [Direction](https://wofsauge.github.io/IsaacDocs/rep/enums/Direction.html)。`Force` 参数将覆盖现有的头部方向锁定，例如使用 “妈妈的刀” 时的锁定。

### SetHeadDirectionLockTime () {: aria-label='Functions' }
#### void SetHeadDirectionLockTime ( int Time ) {: .copyable aria-label='Functions' }
设置玩家头部应强制保持当前方向的时长。

### SetImmaculateConceptionState () {: aria-label='Functions' }
#### void SetImmaculateConceptionState ( int State ) {: .copyable aria-label='Functions' }
如果你设置的值大于 14，该值将自动上限为 14，这意味着下一次拾取红心将生成一个跟班。
请注意，游戏仅在玩家拾取红心时检查是否生成跟班，因此你不能直接使用此函数触发该效果。
设置玩家使用 “圣灵受胎” 道具收集到的红心数量。

### SetItemState () {: aria-label='Functions' }
#### void SetItemState ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
将玩家的道具状态更改为指定道具。这通常用于玩家在激活前举在头顶的道具（如 “鲍勃的烂头”、“玻璃大炮”）。

### SetKeepersSackBonus () {: aria-label='Functions' }
#### void SetKeepersSackBonus ( int Bonus ) {: .copyable aria-label='Functions' }
设置玩家 [“守护者之袋”](https://bindingofisaacrebirth.fandom.com/wiki/Keeper's_Sack) 道具的当前硬币奖励。

### SetLaserColor () {: aria-label='Functions' }
#### void SetLaserColor ( [Color](Color.md) color ) {: .copyable aria-label='Functions' }
设置玩家的激光颜色。

### SetLuckModifier () {: aria-label='Functions' }
#### void SetLuckModifier ( int Modifier ) {: .copyable aria-label='Functions' }
“实验性治疗” 根据随机生成的幸运值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
该修饰符直接添加到玩家的幸运属性上。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### SetMaggySwingCooldown () {: aria-label='Functions' }
#### void SetMaggySwingCooldown ( int Cooldown ) {: .copyable aria-label='Functions' }
将 “堕落抹大拉” 挥击攻击的冷却时间设置为指定的帧数。

### SetMaxBladderCharge () {: aria-label='Functions' }
#### void SetMaxBladderCharge ( int Charge ) {: .copyable aria-label='Functions' }
设置玩家停止射击并为 “肾结石” 道具充能时的最大充能值。

### SetMegaBlastDuration () {: aria-label='Functions' }
#### void SetMegaBlastDuration ( int Duration ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
如果 “巨型爆破” 激光处于激活状态，并且你再次调用此函数并设置较低的持续时间，激光将在指定帧数过去后仍然存在，直到玩家离开房间。
将 “巨型爆破” 激光的持续时间设置为指定的帧数。如果激光尚未激活，将其持续时间设置为大于零的值将激活该效果。

### SetNextUrethraBlockFrame () {: aria-label='Functions' }
#### void SetNextUrethraBlockFrame ( int Frame ) {: .copyable aria-label='Functions' }
设置玩家停止射击并开始为 “肾结石” 道具充能的帧数。

### SetPonyCharge () {: aria-label='Functions' }
#### void SetPonyCharge ( int Time ) {: .copyable aria-label='Functions' }
将 “一匹小马” 和 “白色小马” 道具的充能效果持续时间设置为指定的帧数。

### SetPoopSpell () {: aria-label='Functions' }
#### void SetPoopSpell ( int Slot, [PoopSpellType](https://wofsauge.github.io/IsaacDocs/rep/enums/PoopSpellType.html) PoopSpellType ) {: .copyable aria-label='Functions' }
将便便列表中的指定插槽设置为一种便便类型。这仅由 “堕落？？？” 使用。

### SetPurityState () {: aria-label='Functions' }
#### void SetPurityState ( [PurityState](enums/PurityState.md) State ) {: .copyable aria-label='Functions' }
设置 [“纯洁”](https://bindingofisaacrebirth.fandom.com/wiki/Purity) 道具效果的当前状态。

### SetRedStewBonusDuration () {: aria-label='Functions' }
#### void SetRedStewBonusDuration ( int Duration ) {: .copyable aria-label='Functions' }
将 “红炖菜” 道具的伤害加成持续时间设置为指定的帧数。将持续时间设置为大于 0 的值将激活该效果（如果尚未激活）。

### SetShotSpeedModifier () {: aria-label='Functions' }
#### void SetShotSpeedModifier ( int Modifier ) {: .copyable aria-label='Functions' }
“实验性治疗” 根据随机生成的射击速度值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
为玩家的射击速度增加 `0.2 * 修饰符`。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### SetSpeedModifier () {: aria-label='Functions' }
#### void SetSpeedModifier ( int Modifier ) {: .copyable aria-label='Functions' }
为玩家的移动速度增加 `0.2 * 修饰符`。
“实验性治疗” 根据随机生成的移动速度值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### SetTearPoisonDamage () {: aria-label='Functions' }
#### void SetTearPoisonDamage ( float Damage ) {: .copyable aria-label='Functions' }

___
### SetTearRangeModifier () {: aria-label='Functions' }
#### void SetTearRangeModifier ( int Modifier ) {: .copyable aria-label='Functions' }
为玩家的眼泪射程增加 `2.5 * 修饰符`。
“实验性治疗” 根据随机生成的射程值增加 `-1`、`0` 或 `1`。“虚空” 可能会随机增加 `1`。
用于 “实验性治疗” 和 “虚空” 带来的属性提升。

### SetUrethraBlock () {: aria-label='Functions' }
#### void SetUrethraBlock ( boolean Blocked ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
将 `Blocked` 参数设置为 `false` 似乎没有任何效果。
设置 “肾结石” 道具的眼泪狂轰滥炸攻击是否即将激活。如果玩家没有 “肾结石” 道具，该效果将立即激活。

### SetWeapon () {: aria-label='Functions' }
#### void SetWeapon ( [Weapon](Weapon.md) Weapon, int WeaponSlot ) {: .copyable aria-label='Functions' }
???- info "信息"
始终检查是否为 `nil`，即使是插槽 `1`，因为它可以被模组通过 [Isaac.DestroyWeapon()](Isaac.md#destroyweapon) 删除。
- `4` - 额外武器。
武器插槽及其说明：
- `2` - 额外武器。原版游戏中很少有这种情况，但模组可以填充此插槽。
- `1` - 主武器。
- `3` - 额外武器。
- `0` - 备用武器，如 “缺口斧” 和 “灵魂瓮”。
将指定 `WeaponSlot` 中的活动武器设置为指定武器。

### ShootBlueCandle () {: aria-label='Functions' }
#### void ShootBlueCandle ( [Vector](Vector.md) Direction ) {: .copyable aria-label='Functions' }
使玩家从 “蜡烛” 道具发射蓝色火焰。

### ShuffleCostumes () {: aria-label='Functions' }
#### void ShuffleCostumes ( int Seed = Random( ) ) {: .copyable aria-label='Functions' }
随机化当前的服装。

### SpawnAquariusCreep () {: aria-label='Functions' }
#### [EntityEffect](https://wofsauge.github.io/IsaacDocs/rep/EntityEffect.html) SpawnAquariusCreep ( [TearParams](https://wofsauge.github.io/IsaacDocs/rep/TearParams.html) TearParams = self.TearParams) {: .copyable aria-label='Functions' }
``player->GetTearHitParams(&params, WeaponType.WEAPON_TEARS, (*player->GetTearPoisonDamage() * 0.666f) / player->_damage, -(int)(-Isaac::Random(2) != 0) & 2 - 1, nil)``
???+ info "信息"
供参考，游戏通常是这样计算 `TearParams` 的：
生成一个类似于 “宝瓶座” 产生的爬行效果，包括继承玩家的 `TearParams`。支持传递自定义的 `TearParams`。

### SpawnClot () {: aria-label='Functions' }
#### void SpawnClot ( [Vector](Vector.md) pos, boolean AllowPlayerDeath = false ) {: .copyable aria-label='Functions' } 
作用类似于使用 “吸食器”，移除生命值并生成一个与移除的生命值类型相同的血块。如果设置了 `AllowPlayerDeath`，即使移除的生命值会导致玩家死亡，也会生成一个血块。

### SpawnSaturnusTears () {: aria-label='Functions' }
#### int SpawnSaturnusTears ( ) {: .copyable aria-label='Functions' }
生成一圈类似于 “土星” 道具的眼泪，围绕玩家旋转。

### SwapForgottenForm () {: aria-label='Functions' }
#### void SwapForgottenForm ( boolean Force = false, boolean NoEffects = false) {: .copyable aria-label='Functions' }
如果玩家是 “遗忘者/灵魂”，两者将交换形态。否则，此函数不执行任何操作。
`Force` 参数将强制交换，即使副玩家没有生命值，或者在房间/关卡过渡期间。`NoEffects` 参数将禁用从 “灵魂” 切换到 “遗忘者” 时的灰尘效果和白色渐变效果。

### SyncConsumableCounts () {: aria-label='Functions' }
#### void SyncConsumableCounts ( [EntityPlayer](EntityPlayer.md) Player, int CollectibleFlags ) {: .copyable aria-label='Functions' }      

___
### Teleport () {: aria-label='Functions' }
#### void Teleport ( [Vector](Vector.md) Position, boolean DoEffects = true, boolean TeleportTwinPlayers = false ) {: .copyable aria-label='Functions' }
`DoEffects` 控制是否播放传送动画和音效。`TeleportTwinPlayers` 控制双胞胎玩家（如 “以扫”、拥有 “诞生之权” 的 “堕落拉撒路”）是否与该玩家一起传送。
将玩家传送到房间内的指定位置。

### TriggerRoomClear () {: aria-label='Functions' }
#### void TriggerRoomClear ( ) {: .copyable aria-label='Functions' }
触发玩家身上类似于房间清理的效果（如为主动道具充能）。

### TryAddToBagOfCrafting () {: aria-label='Functions' }
#### void TryAddToBagOfCrafting ( [EntityPickup](EntityPickup.md) Pickup ) {: .copyable aria-label='Functions' }
尝试将指定的拾取物添加到玩家的合成袋中。

### TryDecreaseGlowingHourglassUses () {: aria-label='Functions' }
#### void TryDecreaseGlowingHourglassUses ( int Uses, boolean ForceHourglass = false ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
尝试减少玩家拥有的 “发光沙漏” 道具的剩余使用次数。`ForceHourglass` 参数将立即移除所有充能并将 “发光沙漏” 变为普通沙漏形态。
无论你指定移除的数字有多大，`Uses` 仅减少 1。

### TryFakeDeath () {: aria-label='Functions' }
#### boolean TryFakeDeath ( ) {: .copyable aria-label='Functions' }
在玩家当前位置生成一个玩家的副本，并播放死亡动画和音效。

### TryForgottenThrow () {: aria-label='Functions' }
#### boolean TryForgottenThrow ( [Vector](Vector.md) Direction ) {: .copyable aria-label='Functions' }
如果玩家持有 “堕落遗忘者”，他将朝指定方向被抛出。

### TryPreventDeath () {: aria-label='Functions' }
#### boolean TryPreventDeath ( ) {: .copyable aria-label='Functions' }
成功时返回 `true`，否则返回 `false`。
根据角色的 [HealthType](enums/HealthType.md)，如果角色没有剩余的心之容器，则添加一个以防止死亡。

### TryRemoveSmeltedTrinket () {: aria-label='Functions' }
#### void TryRemoveSmeltedTrinket ( [TrinketType](https://wofsauge.github.io/IsaacDocs/rep/enums/TrinketType.html) ID ) {: .copyable aria-label='Functions' }    
尝试从玩家处移除指定的熔炼饰品。

### UnblockCollectible () {: aria-label='Functions' }
#### void UnblockCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
解除通过 [BlockCollectible](EntityPlayer.md#blockcollectible) 阻挡的 [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html)。

### UpdateIsaacPregnancy () {: aria-label='Functions' }
#### void UpdateIsaacPregnancy ( boolean UpdateCambion ) {: .copyable aria-label='Functions' }
如果你想更新 [“恶魔受胎”](https://bindingofisaacrebirth.fandom.com/wiki/Cambion_Conception) 服装，则设置为 `true`，否则更新 [“圣灵受胎”](https://bindingofisaacrebirth.fandom.com/wiki/Immaculate_Conception) 服装。

### VoidHasCollectible () {: aria-label='Functions' }
#### boolean VoidHasCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
如果指定的道具已被 “虚空” 道具吞噬，则返回 true。