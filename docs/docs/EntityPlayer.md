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
Now accepts an optional `bool` to determine if [EntityPlayer](EntityPlayer.md):EvaluateItems() should be automatically called after adding cache flags. In most cases, you'll want to do this.

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
Now accepts a `Force` argument to forcefully reset the charge instead of only rolling for a change to reset.

### GetCollectibleNum () {: aria-label='Modified Functions' }
#### int GetCollectibleNum ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, boolean OnlyCountTrueItems = false, bool IgnoreSpoof = false ) {: .copyable aria-label='Modified Functions' }
Now accepts a `IgnoreSpoof` argument that ignores innate items.

### GetMultiShotParams () {: aria-label='Modified Functions' }
#### [MultiShotParams](MultiShotParams.md) GetMultiShotParams ( [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html) WeaponType ) {: .copyable aria-label='Modified Functions' }
Now returns a proper `MultiShotParams` object.

### GetMultiShotPositionVelocity () {: aria-label='Modified Functions' }
#### [PosVel](https://wofsauge.github.io/IsaacDocs/rep/PlayerTypes_PosVel.html) GetMultiShotPositionVelocity ( int LoopIndex, [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html) WeaponType, [Vector](Vector.md) ShotDirection, float ShotSpeed, [MultiShotParams](MultiShotParams.md) Params ) {: .copyable aria-label='Modified Functions' }
Compared to the vanilla function, this implementation has been further augmented to throw an error if LoopIndex is higher than [MultiShotParams:GetNumTears()](MultiShotParams.md#getnumtears).
This magically vanished from the API some time after 1.7.8.

### GetPocketItem () {: aria-label='Modified Functions' }
#### [PocketItem](PocketItem.md) GetPocketItem ( [PillCardSlot](enums/PillCardSlot.md) Slot ) {: .copyable aria-label='Modified Functions' }
Gets the card/pill/rune in the specified pocket slot.
Now returns a proper `PocketItem` object.

### HasCollectible () {: aria-label='Modified Functions' }
#### boolean HasCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, boolean IgnoreModifiers = false, boolean IgnoreSpoof = false ) {: .copyable aria-label='Modified Functions' }
Now accepts a `IgnoreSpoof` argument that ignores innate items.

### BabySkin {: aria-label='Modified Variables' }
#### [BabySubType](https://wofsauge.github.io/IsaacDocs/rep/enums/BabySubType.html) BabySkin  {: .copyable aria-label='Modified Variables' }
Same as default, but now returns a proper integer value instead of userdata.

___

## Functions

### AddActiveCharge () {: aria-label='Functions' }
#### int AddActiveCharge ( int Charge, [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot, boolean FlashHUD = true, boolean Overcharge = false, boolean Force = false ) {: .copyable aria-label='Functions' }
Returns the true amount of charge added, which may have been capped by the targeted item's MaxCharge.
???- info "Info"
`FlashHUD` appears to be redundant. Chargebar flashes regardless of using `true` or `false`.

### AddBoneOrbital () {: aria-label='Functions' }
#### void AddBoneOrbital ( [Vector](Vector.md) Position ) {: .copyable aria-label='Functions' }

___
### AddCustomCacheTag () {: aria-label='Functions' }
#### void AddCustomCacheTag ( string OR \{string, string, ...\}, bool EvaluateItems = false ) {: .copyable aria-label='Functions' }
Add CustomCacheTag(s) to be evaluated next time EvaluateItems runs (which is right now, if the optional boolean is passed).
See [items.xml](xml/items.md) for more information on custom caches.

### AddInnateCollectible () {: aria-label='Functions' }
#### void AddInnateCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, int Amount = 1 ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
Currently this function directly modifies the contents of WispCollectiblesList, so if this list was updated on wisp init/delete, or the player exits the run, your added innate items will not be saved.

### AddLeprosy () {: aria-label='Functions' }
#### void AddLeprosy ( ) {: .copyable aria-label='Functions' }
This is currently still capped at a max of three familiars, and would require further modification to change this.
???+ info "Info"

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
???- info "Supported Items"
There are a few items which spawn unique locusts.
- Fire Mind
- Holy Light

### AddSmeltedTrinket () {: aria-label='Functions' }
#### boolean AddSmeltedTrinket ( [TrinketType](https://wofsauge.github.io/IsaacDocs/rep/enums/TrinketType.html) Trinket, boolean FirstTimePickingUp = true ) {: .copyable aria-label='Functions' }
Adds a smelted trinket directly to the player's inventory.
Returns ``true`` if the trinket was successfully added, otherwise ``false``.

### AddUrnSouls () {: aria-label='Functions' }
#### void AddUrnSouls ( int Count = 0 ) {: .copyable aria-label='Functions' }  

___
### BlockCollectible () {: aria-label='Functions' }
#### void BlockCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }  
Blocks the provided [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html). This will make it so the game thinks you don't have the item, even if it's in your inventory.

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
Returns `true` if the player has one of the following items / effects / transformations.
- Mega Mush

### CanOverrideActiveItem () {: aria-label='Functions' }
#### boolean CanOverrideActiveItem ( [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot ) {: .copyable aria-label='Functions' }

___
### CanUsePill () {: aria-label='Functions' }
#### boolean CanUsePill ( [PillEffect](https://wofsauge.github.io/IsaacDocs/rep/enums/PillEffect.html) ID ) {: .copyable aria-label='Functions' }
By some conditions, usually health-related, determines whether a player can use a given pill effect.

### CheckFamiliarEx () {: aria-label='Functions' }
#### [EntityFamiliar](EntityFamiliar.md)[] CheckFamiliarEx ( int [FamiliarVariant](https://wofsauge.github.io/IsaacDocs/rep/enums/FamiliarVariant.html) Familiar, int TargetCount, [RNG](RNG.md) rng, [ItemConfigItem](ItemConfig_Item.md) SourceItemConfigItem = nil, int FamiliarSubType = -1 ) {: .copyable aria-label='Functions' }
A version of [CheckFamiliar](https://wofsauge.github.io/IsaacDocs/rep/EntityPlayer.html#checkfamiliar) that returns all familiars spawned by the function as a table.

### ClearCollectibleAnim () {: aria-label='Functions' }
#### void ClearCollectibleAnim ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible) {: .copyable aria-label='Functions' }

___
### ClearQueueItem () {: aria-label='Functions' }
#### void ClearQueueItem ( ) {: .copyable aria-label='Functions' }

___
### DropCollectible () {: aria-label='Functions' }
#### void DropCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, [EntityPickup](EntityPickup.md) ExistingPedestal = nil, boolean RemoveFromPlayerForm = false ) {: .copyable aria-label='Functions' }
If `ExistingPedestal` is set, the collectible it contains will be swapped out for the dropped collectible instead of a new pedestal spawning.

### DropCollectibleByHistoryIndex () {: aria-label='Functions' }
#### [EntityPickup](EntityPickup.md) DropCollectibleByHistoryIndex ( int Idx, [EntityPickup](EntityPickup.md) ExistingPedestal = nil ) {: .copyable aria-label='Functions' }
If `ExistingPedestal` is set, the collectible it contains will be swapped out for the dropped collectible instead of a new pedestal spawning.

### EnableWeaponType () {: aria-label='Functions' }
#### void EnableWeaponType ( [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html) Weapon, boolean Set ) {: .copyable aria-label='Functions' }

___
### FireBrimstoneBall () {: aria-label='Functions' }
#### [EntityEffect](EntityEffect.md) FireBrimstoneBall ( [Vector](Vector.md) Position, [Vector](Vector.md) Velocity, [Vector](Vector.md) Offset = Vector.Zero ) {: .copyable aria-label='Functions' }
If the player has Tech X, this function will fire an [EntityLaser](EntityLaser.md) as well. The laser will have the Brimstone ball effect as a parent, it's unclear if the effect also links back to the laser.
???+ info "Info"

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
Gets the current content of the bag in the given `SlotID`.

### GetBladderCharge () {: aria-label='Functions' }
#### int GetBladderCharge ( ) {: .copyable aria-label='Functions' }
Returns the current charge for when the player stops shooting and charges the Kidney Stone item.

### GetBloodLustCounter () {: aria-label='Functions' }
#### int GetBloodLustCounter ( ) {: .copyable aria-label='Functions' }

___
### GetBodyMoveDirection () {: aria-label='Functions' }
#### [Vector](Vector.md) GetBodyMoveDirection ( ) {: .copyable aria-label='Functions' }

___
### GetBombPlaceDelay () {: aria-label='Functions' }
#### int GetBombPlaceDelay ( ) {: .copyable aria-label='Functions' }
Default bomb place delay is `30 frames`.

### GetCambionConceptionState () {: aria-label='Functions' }
#### int GetCambionConceptionState ( ) {: .copyable aria-label='Functions' }
Returns how many times the player has taken damage with the Cambion Conception item.

### GetCambionPregnancyLevel () {: aria-label='Functions' }
#### int GetCambionPregnancyLevel ( ) {: .copyable aria-label='Functions' }
Corresponds to the current visible state of Cambion Conception's costume (0-2).

### GetCollectiblesList () {: aria-label='Functions' }
#### table GetCollectiblesList ( ) {: .copyable aria-label='Functions' }
Returns a table with the amount of each collectible the player has, without counting innate items.
print(collectiblesList[CollectibleType.COLLECTIBLE_SAD_ONION])
```lua
local collectiblesList = player:GetCollectiblesList()
This code prints how many sad onions the player has.
???- example "Example Code"
```

### GetConceptionFamiliarFlags () {: aria-label='Functions' }
#### int GetConceptionFamiliarFlags ( ) {: .copyable aria-label='Functions' }
Returns the bitmask corresponding to which familiars have been spawned by Cambion/Immaculate Conception. The additional familiars provided by this bitmask are spawned during familiar cache evaluation, but only while the player has one of those two items.

### GetCostumeLayerMap () {: aria-label='Functions' }
#### table GetCostumeLayerMap ( ) {: .copyable aria-label='Functions' }
local map = Isaac.GetPlayer():GetCostumeLayerMap()
print(layer - 1, "-", layerName, "-", costumeName, "-", spritePath)
local costumeSpriteDescs = player:GetCostumeSpriteDescs()
Below is a snippet of code that displays all currently occupied costume layers.
```lua
print("-------------------------------------------------------------------")
| priority | int | Costume's priority as listed in `costumes2.xml`. `-1` if no costume is on that layer. |
local costumeSpriteDesc = costumeSpriteDescs[mapData.costumeIndex + 1]
local sprite = costumeSpriteDesc:GetSprite()
if mapData.costumeIndex == -1 then goto continue end
| costumeIndex | int | Index of active/visible costume for that layer.  `-1` if no costume is on that layer. |
Returns table of player sprite layers data for costumes with the following fields:
| isBodyLayer | boolean | `true` if the costume is a body costume. `false` if not or if no costume is on that layer. |
local costumeName = itemConfig.Name ~= "" and Isaac.GetString("Items", itemConfig.Name) or "NullItemID "..itemConfig.ID
|:--|:--|:--|
The returned table's index order corresponds to PlayerSpriteLayer. However, due to the differences in the starting index of arrays between Lua and C++, CostumeLayerMap's index needs to be decreased by 1 and it's costumeIndex increased by 1 in order to get accurate information.
end
for layer, mapData in ipairs(map) do
Prints are sectioned as such: PlayerSpriteLayer - Layer Name - Item Name/NullItemID - Anm2 filepath
| layerID | int | ID of the sprite's layer corresponding to its anm2 file. `-1` if no costume is on that layer. |
local layerName = sprite:GetLayer(mapData.layerID):GetName()
???- info "More Layer Map Info"
local player = Isaac.GetPlayer()
|Field|Type|Comment|
local spritePath = sprite:GetFilename()
local itemConfig = costumeSpriteDesc:GetItemConfig()
???+ example "Example Code"
::continue::
```

### GetCostumeSpriteDescs () {: aria-label='Functions' }
#### [CostumeSpriteDesc](CostumeSpriteDesc.md)[] GetCostumeSpriteDescs ( ) {: .copyable aria-label='Functions' }
Returns a table of [CostumeSpriteDesc](CostumeSpriteDesc.md).

### GetCustomCacheValue () {: aria-label='Functions' }
#### float GetCustomCacheValue ( string CustomCacheTag ) {: .copyable aria-label='Functions' }
Returns the current cached value for the specified CustomCacheTag. Will return `0` by default if the provided tag has not been evaluated.
See [items.xml](xml/items.md) for more information on custom caches.

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
Modifier is applied to the player as flat damage.
Experimental Treatment adds `-1`, `0` or `1` depending on the damage rolled. Void may randomly add `1`.
Used for Experimental Treatment and for stat boosts from Void.

### GetDeadEyeCharge () {: aria-label='Functions' }
#### int GetDeadEyeCharge ( ) {: .copyable aria-label='Functions' }

___
### GetDeathAnimName () {: aria-label='Functions' }
#### string GetDeathAnimName ( ) {: .copyable aria-label='Functions' }
- `LostDeath` - When playing as the Lost, under the Lost Curse, playing as Forgotten's Soul, or in Tainted Jacob's Ghost form.
Returns the name of the player's death animation.
This can return the following strings:
- `Death` - The regular death animation name.
???+ info "Return info"

### GetEdenDamage () {: aria-label='Functions' }
#### float GetEdenDamage ( ) {: .copyable aria-label='Functions' }
Returns the offset of the player's damage stat for Eden's random stats.

### GetEdenFireDelay () {: aria-label='Functions' }
#### float GetEdenFireDelay ( ) {: .copyable aria-label='Functions' }
Returns the offset of the player's fire delay stat for Eden's random stats.

### GetEdenLuck () {: aria-label='Functions' }
#### float GetEdenLuck ( ) {: .copyable aria-label='Functions' }
Returns the offset of the player's luck stat for Eden's random stats.

### GetEdenRange () {: aria-label='Functions' }
#### float GetEdenRange ( ) {: .copyable aria-label='Functions' }
Returns the offset of the player's range stat for Eden's random stats.

### GetEdenShotSpeed () {: aria-label='Functions' }
#### float GetEdenShotSpeed ( ) {: .copyable aria-label='Functions' }
Returns the offset of the player's shot speed stat for Eden's random stats.

### GetEdenSpeed () {: aria-label='Functions' }
#### float GetEdenSpeed ( ) {: .copyable aria-label='Functions' }
Returns the offset of the player's speed stat for Eden's random stats.

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
Returns the current charge of Tainted Eve's innate Sumptorium ability.

### GetFireDelayModifier () {: aria-label='Functions' }
#### int GetFireDelayModifier ( ) {: .copyable aria-label='Functions' }
Experimental Treatment adds `-1`, `0` or `1` depending on the fire delay rolled. Void may randomly add `1`.
Grants `0.5 * modifier` flat tears per second to the player.
Used for Experimental Treatment and for stat boosts from Void.

### GetFlippedForm () {: aria-label='Functions' }
#### [EntityPlayer](EntityPlayer.md) GetFlippedForm ( ) {: .copyable aria-label='Functions' }
Returns flipped form of the current character. (only used for Tainted Lazarus)
Otherwise, returns `nil`.

### GetFocusEntity () {: aria-label='Functions' }
#### [Entity](Entity.md) GetFocusEntity ( ) {: .copyable aria-label='Functions' }
Returns the entity used by Active Camera to determine where the camera should focus. This can be either the [Marked](https://bindingofisaacrebirth.fandom.com/wiki/Marked) target [EntityEffect](EntityEffect.md) or a weapon's entity.
If none of these exist, this returns `nil`.

### GetFootprintColor () {: aria-label='Functions' }
#### [KColor](https://wofsauge.github.io/IsaacDocs/rep/KColor.html) GetFootprintColor ( boolean LeftFootprint ) {: .copyable aria-label='Functions' }

___
### GetGlitchBabySubType () {: aria-label='Functions' }
#### int GetGlitchBabySubType ( ) {: .copyable aria-label='Functions' }

___
### GetGlyphOfBalanceDrop () {: aria-label='Functions' }
#### table GetGlyphOfBalanceDrop ( int Variant = -1, int SubType = -1 ) {: .copyable aria-label='Functions' }
Returns a table containing the variant and subtype of the possible [Glyph of Balance](https://bindingofisaacrebirth.fandom.com/wiki/Glyph_of_Balance) drop.

### GetGnawedLeafTimer () {: aria-label='Functions' }
#### int GetGnawedLeafTimer ( ) {: .copyable aria-label='Functions' }

___
### GetGreedsGulletHearts () {: aria-label='Functions' }
#### int GetGreedsGulletHearts ( ) {: .copyable aria-label='Functions' }

___
### GetHallowedGroundCountdown () {: aria-label='Functions' }
#### int GetHallowedGroundCountdown ( ) {: .copyable aria-label='Functions' }
Returns the grace period countdown of retaining stats from the Hallowed Ground/Star of Bethlehem aura.

### GetHeadDirectionLockTime () {: aria-label='Functions' }
#### int GetHeadDirectionLockTime ( ) {: .copyable aria-label='Functions' }
How long the player's head should be forced to stay in its current direction. `-1` (or lower) indicates the direction is not currently locked.

### GetHealthType () {: aria-label='Functions' }
#### [HealthType](enums/HealthType.md) GetHealthType ( ) {: .copyable aria-label='Functions' }

___
### GetHeldEntity () {: aria-label='Functions' }
#### [Entity](Entity.md) GetHeldEntity ( ) {: .copyable aria-label='Functions' }
Returns `nil` if no entity is currently being held.
Returns the Entity that the player is holding over their head, such as with throwable red bombs or [Suplex!](https://bindingofisaacrebirth.fandom.com/wiki/Suplex!)

### GetHeldSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetHeldSprite ( ) {: .copyable aria-label='Functions' }
Gets the [Sprite](Sprite.md) object used for when the player is doing an animation that involves holding a sprite over their head, such as active item usage.

### GetHistory () {: aria-label='Functions' }
#### [History](History.md) GetHistory ( ) {: .copyable aria-label='Functions' }

___
### GetImmaculateConceptionState () {: aria-label='Functions' }
#### int GetImmaculateConceptionState ( ) {: .copyable aria-label='Functions' }
Returns how many hearts have been collected with the Immaculate Conception item. Resets to 0 after spawning a familiar/soul heart.

### GetKeepersSackBonus () {: aria-label='Functions' }
#### int GetKeepersSackBonus ( ) {: .copyable aria-label='Functions' }
Gets the number of coins spent while possessing [Keeper's Sack](https://bindingofisaacrebirth.fandom.com/wiki/Keeper's_Sack).

### GetLaserColor () {: aria-label='Functions' }
#### [Color](Color.md) GetLaserColor ( ) {: .copyable aria-label='Functions' }

___
### GetLuckModifier () {: aria-label='Functions' }
#### int GetLuckModifier ( ) {: .copyable aria-label='Functions' }
Experimental Treatment adds `-1`, `0` or `1` depending on the luck rolled. Void may randomly add `1`.
The modifier is added directly to the player's Luck stat.
Used for Experimental Treatment and for stat boosts from Void.

### GetMaggySwingCooldown () {: aria-label='Functions' }
#### int GetMaggySwingCooldown ( ) {: .copyable aria-label='Functions' }
Returns the amount of frames left until Tainted Magdalene's swing attack from being damaged can be used again. Returns `0` if the player is not Tainted Magdalene.

### GetMarkedTarget () {: aria-label='Functions' }
#### [EntityEffect](https://wofsauge.github.io/IsaacDocs/rep/EntityEffect.html) GetMarkedTarget ( ) { : .copyable aria-label='Functions' }
If the target is not displayed on the ground, this function returns `nil`.
Returns the entity effect representing the target of the [Marked](https://bindingofisaacrebirth.fandom.com/wiki/Marked) item.

### GetMaxBladderCharge () {: aria-label='Functions' }
#### int GetMaxBladderCharge ( ) {: .copyable aria-label='Functions' }
Returns the maximum charge for when the player stops shooting and charges the Kidney Stone item.

### GetMaxBombs () {: aria-label='Functions' }
#### int GetMaxBombs ( ) {: .copyable aria-label='Functions' }
Returns the maximum number of bombs the player can currently hold.

### GetMaxCoins () {: aria-label='Functions' }
#### int GetMaxCoins ( ) {: .copyable aria-label='Functions' }
Returns the maximum number of coins the player can currently hold.

### GetMaxKeys () {: aria-label='Functions' }
#### int GetMaxKeys ( ) {: .copyable aria-label='Functions' }
Returns the maximum number of keys the player can currently hold.

### GetMaxPeeBurstCooldown () {: aria-label='Functions' }
#### int GetMaxPeeBurstCooldown ( ) {: .copyable aria-label='Functions' }
Returns the maximum attack duration of the Kidney Stone item.

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
Returns the pickups that are stored on the player through the use of the Moving Box collectible.

### GetNextUrethraBlockFrame () {: aria-label='Functions' }
#### int GetNextUrethraBlockFrame ( ) {: .copyable aria-label='Functions' }
Returns the frame at which the player stops shooting and starts charging the [Kidney Stone](https://bindingofisaacrebirth.fandom.com/wiki/Kidney_Stone) item.

### GetPeeBurstCooldown () {: aria-label='Functions' }
#### int GetPeeBurstCooldown ( ) {: .copyable aria-label='Functions' }
Returns the attack duration of the [Kidney Stone](https://bindingofisaacrebirth.fandom.com/wiki/Kidney_Stone) item.

### GetPlayerFormCounter () {: aria-label='Functions' }
#### int GetPlayerFormCounter ( [PlayerForm](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerForm.html) PlayerFormID ) {: .copyable aria-label='Functions' } 
Returns the amount of collectibles the player has tied to the specified transformation.

### GetPlayerIndex () {: aria-label='Functions' }
#### int GetPlayerIndex ( ) {: .copyable aria-label='Functions' }

___
### GetPonyCharge () {: aria-label='Functions' }
#### int GetPonyCharge ( ) {: .copyable aria-label='Functions' }
Returns the amount of frames left until the charging effect from the A Pony or White Pony item deactivates.

### GetPurityState () {: aria-label='Functions' }
#### [PurityState](enums/PurityState.md) GetPurityState ( ) {: .copyable aria-label='Functions' }
Returns the state in which the [Purity](https://bindingofisaacrebirth.fandom.com/wiki/Purity) item effect currently is. Returns `PurityState.BLUE` if the player does not have the Purity collectible.

### GetRedStewBonusDuration () {: aria-label='Functions' }
#### int GetRedStewBonusDuration ( ) {: .copyable aria-label='Functions' }
Returns the frames left until the damage bonus from Red Stew expires.

### GetShotSpeedModifier () {: aria-label='Functions' }
#### int GetShotSpeedModifier ( ) {: .copyable aria-label='Functions' }
Experimental Treatment adds `-1`, `0` or `1` depending on the shot speed rolled. Void may randomly add `1`.
Adds `0.2 * modifier` to the player's ShotSpeed.
Used for Experimental Treatment and for stat boosts from Void.

### GetSmeltedTrinkets () {: aria-label='Functions' }
#### table GetSmeltedTrinkets ( ) {: .copyable aria-label='Functions' }
Returns a table of smelted trinkets and their corresponding amounts. The returned table contains the following fields:
|:--|:--|:--|
|Field|Type|Comment|
| goldenTrinketAmount | int | |
| trinketAmount | int | |

### GetSpecialGridCollision () {: aria-label='Functions' }
#### int GetSpecialGridCollision ( [Vector](Vector.md) Position = self.Position ) {: .copyable aria-label='Functions' }      

___
### GetSpeedModifier () {: aria-label='Functions' }
#### int GetSpeedModifier ( ) {: .copyable aria-label='Functions' }
Adds `0.2 * modifier` to the player's MoveSpeed.
Experimental Treatment adds `-1`, `0` or `1` depending on the speed rolled. Void may randomly add `1`.
Used for Experimental Treatment and for stat boosts from Void.

### GetSpoofedCollectiblesList () {: aria-label='Functions' }
#### table[] GetSpoofedCollectiblesList ( ) {: .copyable aria-label='Functions' }
| IsBlocked | boolean | |
| CollectibleID | [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) | |
|:--|:--|:--|
|Field|Type|Comment|
| AppendedCount | int | |

### GetTearDisplacement () {: aria-label='Functions' }
#### int GetTearDisplacement ( ) {: .copyable aria-label='Functions' }
- `1` Right eye
???+ info "Return info"
- `-1` Left eye
Returns the player's TearDisplacement value, used to check what eye the player is shooting from.

### GetTotalActiveCharge () {: aria-label='Functions' }
#### int GetTotalActiveCharge ( [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot ) {: .copyable aria-label='Functions' }

___
### GetUrnSouls () {: aria-label='Functions' }
#### int GetUrnSouls ( ) {: .copyable aria-label='Functions' }

___
### GetVoidedCollectiblesList () {: aria-label='Functions' }
#### [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html)[] GetVoidedCollectiblesList ( ) {: .copyable aria-label='Functions' }
Retuns a table containing the [CollectibleTypes](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) of all voided Active items.

### GetWeapon () {: aria-label='Functions' }
#### [Weapon](Weapon.md) GetWeapon ( int Slot ) {: .copyable aria-label='Functions' }
???- info "Info"
Always check for `nil`, even for slot `1` as it can be deleted by mods via [Isaac.DestroyWeapon()](Isaac.md#destroyweapon).
- `4` - Additional Weapon.
Weapon slots and their descriptions:
Returns the Weapon object in the corresponding slot, or `nil` if no Weapon can be found. Slot needs to be between `0` and `4`.
- `2` - Additional Weapon. Few instances of this exist in the vanilla game, but it can be populated by mods.
- `1` - Primary Weapon.
- `3` - Additional Weapon.
- `0` - Backup Weapon such as Notched Axe and Urn of Souls.

### GetWeaponModifiers () {: aria-label='Functions' }
#### int GetWeaponModifiers ( ) {: .copyable aria-label='Functions' }
Returns a bitmask of [WeaponModifiers](enums/WeaponModifier.md).

### GetWildCardItem () {: aria-label='Functions' }
#### int GetWildCardItem ( ) {: .copyable aria-label='Functions' }
If the player used an active item, its `CollectibleType` is returned. If the player used a consumable, its variant is returned. If the player used ? Mark Card, returns `1`. If no active item had ever been used by the player before, turns `0`.
Returns the item that was last used by the player and would be activated again upon using Wild Card.

### GetWildCardItemType () {: aria-label='Functions' }
#### [PocketItemType](enums/PocketItemType.md) GetWildCardItemType ( ) {: .copyable aria-label='Functions' }
Returns the type of item that was last used by the player and would be activated again upon using Wild Card.
If the player used a consumable (including ? Mark Card), returns `ItemType.ITEM_PASSIVE`. If no active item had been used by the player before, returns `255`.

### GetWispCollectiblesList () {: aria-label='Functions' }
#### table GetWispCollectiblesList ( ) {: .copyable aria-label='Functions' }
Returns a table of [CollectibleTypes](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) corresponding to the item wisps the player has.

### HasChanceRevive () {: aria-label='Functions' }
#### boolean HasChanceRevive ( ) {: .copyable aria-label='Functions' }
Returns true if a "?" would be displayed on the player's extra life count (ie, the player has Guppy's Collar, or a modded revive item with the `chancerevive` string in REPENTOGON's [customtags items.xml attribute](xml/items.md)).

### HasGoldenTrinket () {: aria-label='Functions' }
#### boolean HasGoldenTrinket ( [TrinketType](https://wofsauge.github.io/IsaacDocs/rep/enums/TrinketType.html) Trinket ) {: .copyable aria-label='Functions' }
Returns true if you have a golden variant of the provided [TrinketType](https://wofsauge.github.io/IsaacDocs/rep/enums/TrinketType.html).

### HasInstantDeathCurse () {: aria-label='Functions' }
#### boolean HasInstantDeathCurse ( ) {: .copyable aria-label='Functions' }
Returns true when the player is in the Lost form triggered by either the white fire in Downpour or Soul of The Lost. (or when in Tainted Jacob's ghost form when being touched by Dark Esau)

### HasPoisonImmunity () {: aria-label='Functions' }
#### boolean HasPoisonImmunity ( ) {: .copyable aria-label='Functions' }

___
### IncrementPlayerFormCounter () {: aria-label='Functions' }
#### void IncrementPlayerFormCounter ( [PlayerForm](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerForm.html) Form, int Count ) {: .copyable aria-label='Functions' }
Increases or decreases the counter towards one of the player's transformations. `Count` can be negative to decrement the [PlayerForm](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerForm.html).

### InitPostLevelInitStats () {: aria-label='Functions' }
#### void InitPostLevelInitStats ( ) {: .copyable aria-label='Functions' }
Call this after spawning characters with "special" tears (Forgotten, Lilith, Azazel etc) with InitTwin, or they won't have their proper tear type.

### InitTwin () {: aria-label='Functions' }
#### [EntityPlayer](EntityPlayer.md) InitTwin ( [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) PlayerType ) {: .copyable aria-label='Functions' }
Initializes a new player that is controlled by the player's same controller.
???+ bug "Bug"
We've received confirmation from \_Kilburn that this is hardcoded to be handled on vanilla characters. We will need to add a workaround for this.
The twin player will desync from its main twin on save and continue. This softlocks the game in singleplayer, as the game prompts for a controller.

### IsCollectibleAnimFinished () {: aria-label='Functions' }
#### boolean IsCollectibleAnimFinished ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, string Animation ) {: .copyable aria-label='Functions' }
Returns true if the animation associated with the collectible is visible.

### IsCollectibleBlocked () {: aria-label='Functions' }
#### boolean IsCollectibleBlocked ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
Returns true if the [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) was blocked. Collectibles can only be blocked by use of [BlockCollectible](EntityPlayer.md#blockcollectible).

### IsCollectibleCostumeVisible () {: aria-label='Functions' }
#### boolean IsCollectibleCostumeVisible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, int PlayerSpriteLayerID ) {: .copyable aria-label='Functions' }
Returns `true` if the costume associated with the collectible is visible.

### IsEntityValidTarget () {: aria-label='Functions' }
#### boolean IsEntityValidTarget ( [Entity](Entity.md) Entity ) {: .copyable aria-label='Functions' }

___
### IsFootstepFrame () {: aria-label='Functions' }
#### boolean IsFootstepFrame ( int Foot = -1 ) {: .copyable aria-label='Functions' }       
- `0` - Returns true every 24 frames.
???+ info "Info"
- `1` - Always false.
- `-1` - Returns true every 12 frames.

### IsHeadless () {: aria-label='Functions' }
#### boolean IsHeadless ( ) {: .copyable aria-label='Functions' }
Returns `true` is the player is headless due to collectibles such as Guillotine, The Intruder, Scissors, and Decap Attack.

### IsHologram () {: aria-label='Functions' }
#### boolean IsHologram ( ) {: .copyable aria-label='Functions' }
Returns `true` if the player is the non-active form of Tainted Lazarus with Birthright.

### IsInvisible () {: aria-label='Functions' }
#### boolean IsInvisible ( ) {: .copyable aria-label='Functions' }
Returns `true` if the player has the Faded Polaroid / Camo Undies effect active.

### IsItemCostumeVisible () {: aria-label='Functions' }
#### boolean IsItemCostumeVisible ( [ItemConfig_Item](ItemConfig_Item.md) Item, int PlayerSpriteLayerID ) {: .copyable aria-label='Functions' }
#### boolean IsItemCostumeVisible ( [ItemConfig_Item](ItemConfig_Item.md) Item, int PlayerSpriteLayerName ) {: .copyable aria-label='Functions' }

___
### IsLocalPlayer () {: aria-label='Functions' }
#### boolean IsLocalPlayer ( ) {: .copyable aria-label='Functions' }
For online play. Returns `true` if you're a local player, `false` otherwise.

### IsNullItemCostumeVisible () {: aria-label='Functions' }
#### boolean IsNullItemCostumeVisible ( int nullItem, int layerID = 0 ) {: .copyable aria-label='Functions' }
#### boolean IsNullItemCostumeVisible ( int nullItem, string layerName ) {: .copyable aria-label='Functions' }

___
### IsPacifist () {: aria-label='Functions' }
#### boolean IsPacifist ( ) {: .copyable aria-label='Functions' }

___
### IsUrethraBlocked () {: aria-label='Functions' }
#### boolean IsUrethraBlocked ( ) {: .copyable aria-label='Functions' }
Returns true when the player can no longer shoot due to charging the [Kidney Stone](https://bindingofisaacrebirth.fandom.com/wiki/Kidney_Stone) item.

### MorphToCoopGhost () {: aria-label='Functions' }
#### void MorphToCoopGhost ( ) {: .copyable aria-label='Functions' }
Turns the player into a co-op ghost.

### PlayCollectibleAnim () {: aria-label='Functions' }
#### void PlayCollectibleAnim ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, boolean CheckBodyLayers, string AnimationName, int Frame = -1 ) {: .copyable aria-label='Functions' }
Plays an animation tied to the provided collectible.

### PlayDelayedSFX () {: aria-label='Functions' }
#### void PlayDelayedSFX ( [SoundEffect](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) ID, int SoundDelay = 0, int FrameDelay = 2, float Volume = 1.0 ) {: .copyable aria-label='Functions' }
Plays a sound effect after a delay.

### RemoveCollectibleByHistoryIndex () {: aria-label='Functions' }
#### void RemoveCollectibleByHistoryIndex ( int Index ) {: .copyable aria-label='Functions' }
Removes the collectible from the player associated with the specified history index.

### RemovePocketItem () {: aria-label='Functions' }
#### void RemovePocketItem ( [PillCardSlot](enums/PillCardSlot.md) Slot ) {: .copyable aria-label='Functions' }

___
### RemovePoopSpell () {: aria-label='Functions' }
#### void RemovePoopSpell ( int Position = 0 ) {: .copyable aria-label='Functions' }
Removes the poop spell from the specified queue position and shifts all spells after it forward to fill the space. A new spell is randomly picked to fill the last position. Poop spells are only used by Tainted ???.

### RerollAllCollectibles () {: aria-label='Functions' }
#### void RerollAllCollectibles ( [RNG](RNG.md) rng, boolean includeActiveItems ) {: .copyable aria-label='Functions' }
Rerolls all of the player's collectibles.

### ResetPlayer () {: aria-label='Functions' }
#### void ResetPlayer ( ) {: .copyable aria-label='Functions' }
This is used by the Genesis active item.
???+ info "Info"

### ReviveCoopGhost () {: aria-label='Functions' }
#### boolean ReviveCoopGhost ( ) {: .copyable aria-label='Functions' }

___
### SalvageCollectible () {: aria-label='Functions' }
#### void SalvageCollectible ( [EntityPickup](EntityPickup.md) Pickup, [RNG](RNG.md) rng = PickupDropRNG, [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) Pool = ItemPoolType.POOL_NULL) {: .copyable aria-label='Functions' }
The provided [EntityPickup](EntityPickup.md) will be removed by this function. Use the override to avoid this.
???+ info "Info"
Produces a random quantity of various pickups, similar to Tainted Cain's ability.

### SetActiveVarData () {: aria-label='Functions' }
#### void SetActiveVarData ( int VarData, [ActiveSlot](https://wofsauge.github.io/IsaacDocs/rep/enums/ActiveSlot.html) Slot ) {: .copyable aria-label='Functions' }

___
### SetBagOfCraftingContent () {: aria-label='Functions' }
#### void SetBagOfCraftingContent ( [BagOfCraftingPickup](enums/BagOfCraftingPickup.md)[] ContentTable ) {: .copyable aria-label='Functions' }
Sets the content of the bag to the content of the table. Table must use valid [BagOfCraftingPickup](enums/BagOfCraftingPickup.md) ids. Table can be shorter than 8, in which case the remaining indexes are set to empty.

### SetBagOfCraftingOutput () {: aria-label='Functions' }
#### void SetBagOfCraftingOutput ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
Sets the output of the player's Bag of Crafting to the specified collectible.

### SetBagOfCraftingSlot () {: aria-label='Functions' }
#### void SetBagOfCraftingSlot ( int SlotID, [BagOfCraftingPickup](enums/BagOfCraftingPickup.md) PickupID ) {: .copyable aria-label='Functions' }
Sets the specified slot in the player's Bag of Crafting to the specified pickup.

### SetBlackHeart () {: aria-label='Functions' }
#### void SetBlackHeart ( int BlackHeart ) {: .copyable aria-label='Functions' }

___
### SetBladderCharge () {: aria-label='Functions' }
#### void SetBladderCharge ( int Charge ) {: .copyable aria-label='Functions' }
Used by the [Kidney Stone](https://bindingofisaacrebirth.fandom.com/wiki/Kidney_Stone) item.
???+ bug "Bug"
The player's head turns pitch black when this function is used without Kidney Stone.

### SetBloodLustCounter () {: aria-label='Functions' }
#### void SetBloodLustCounter ( int Counter ) {: .copyable aria-label='Functions' }

___
### SetBombPlaceDelay () {: aria-label='Functions' }
#### void SetBombPlaceDelay ( int Delay ) {: .copyable aria-label='Functions' }

___
### SetCambionConceptionState () {: aria-label='Functions' }
#### void SetCambionConceptionState ( int State ) {: .copyable aria-label='Functions' }
Note that the game only spawns a familiar when the player takes damage, if this counter is now at 15, 30, 60 or 90. You cannot trigger a birth directly with this function.
Sets how much damage has been taken for the Cambion Conception item.

### SetCanShoot () {: aria-label='Functions' }
#### boolean SetCanShoot ( boolean CanShoot ) {: .copyable aria-label='Functions' }
Instantaneously disables (or enables) the player's ability to shoot. The base game primarily uses this for special challenges.

### SetConceptionFamiliarFlags () {: aria-label='Functions' }
#### void SetConceptionFamiliarFlags ( [ConceptionFamiliarFlag](enums/ConceptionFamiliarFlag.md) Flags ) {: .copyable aria-label='Functions' }
Sets the bitmask corresponding to which familiars have been spawned by Cambion/Immaculate Conception. The additional familiars provided by this bitmask are spawned during familiar cache evaluation, but only while the player has one of those two items.

### SetControllerIndex () {: aria-label='Functions' }
#### void SetControllerIndex ( int Idx ) {: .copyable aria-label='Functions' }        
Changes the player's controller index.

### SetDamageModifier () {: aria-label='Functions' }
#### void SetDamageModifier ( int Modifier ) {: .copyable aria-label='Functions' }
Modifier is applied to the player as flat damage.
Experimental Treatment adds `-1`, `0` or `1` depending on the damage rolled. Void may randomly add `1`.
Used for Experimental Treatment and for stat boosts from Void.

### SetEdenDamage () {: aria-label='Functions' }
#### void SetEdenDamage ( float Value ) {: .copyable aria-label='Functions' }
Sets the offset of the player's damage stat for Eden's random stats. Has no effect on players that aren't Eden or Tainted Eden.

### SetEdenFireDelay () {: aria-label='Functions' }
#### void SetEdenFireDelay ( float Value ) {: .copyable aria-label='Functions' }
Sets the offset of the player's fire delay stat for Eden's random stats. Has no effect on players that aren't Eden or Tainted Eden.

### SetEdenLuck () {: aria-label='Functions' }
#### void SetEdenLuck ( float Value ) {: .copyable aria-label='Functions' }
Sets the offset of the player's luck stat for Eden's random stats. Has no effect on players that aren't Eden or Tainted Eden.

### SetEdenRange () {: aria-label='Functions' }
#### void SetEdenRange ( float Value ) {: .copyable aria-label='Functions' }
Sets the offset of the player's range stat for Eden's random stats. Has no effect on players that aren't Eden or Tainted Eden.

### SetEdenShotSpeed () {: aria-label='Functions' }
#### void SetEdenShotSpeed ( float Value ) {: .copyable aria-label='Functions' }
Sets the offset of the player's shot speed stat for Eden's random stats. Has no effect on players that aren't Eden or Tainted Eden.

### SetEdenSpeed () {: aria-label='Functions' }
#### void SetEdenSpeed ( float Value ) {: .copyable aria-label='Functions' }
Sets the offset of the player's speed stat for Eden's random stats. Has no effect on players that aren't Eden or Tainted Eden.

### SetEveSumptoriumCharge () {: aria-label='Functions' }
#### void SetEveSumptoriumCharge ( int ChargeNum ) {: .copyable aria-label='Functions' }
Sets the current charge of Tainted Eve's innate Sumptorium ability.

### SetFireDelayModifier () {: aria-label='Functions' }
#### void SetFireDelayModifier ( int Modifier ) {: .copyable aria-label='Functions' }
Experimental Treatment adds `-1`, `0` or `1` depending on the fire delay rolled. Void may randomly add `1`.
Grants `0.5 * modifier` flat tears per second to the player.
Used for Experimental Treatment and for stat boosts from Void.

### SetFootprintColor () {: aria-label='Functions' }
#### void SetFootprintColor ( [KColor](https://wofsauge.github.io/IsaacDocs/rep/KColor.html) color, boolean RightFoot = false ) {: .copyable aria-label='Functions' }
Sets the player's footprint color.
???+ bug "Bug"
This function currently crashes the game - will be fixed in a future update.

### SetGnawedLeafTimer () {: aria-label='Functions' }
#### void SetGnawedLeafTimer ( int Timer ) {: .copyable aria-label='Functions' }

___
### SetHallowedGroundCountdown () {: aria-label='Functions' }
#### void SetHallowedGroundCountdown ( int Countdown ) {: .copyable aria-label='Functions' }
Sets the grace period countdown of retaining stats from the Hallowed Ground/Star of Bethlehem aura.

### SetHeadDirection () {: aria-label='Functions' }
#### void SetHeadDirection ( [Direction](https://wofsauge.github.io/IsaacDocs/rep/enums/Direction.html) Direction, int Time, boolean Force = false ) {: .copyable aria-label='Functions' }
Locks the player's head animation to the specified [Direction](https://wofsauge.github.io/IsaacDocs/rep/enums/Direction.html). `Force` will override existing head direction locks, such as the one from firing Mom's Knife.

### SetHeadDirectionLockTime () {: aria-label='Functions' }
#### void SetHeadDirectionLockTime ( int Time ) {: .copyable aria-label='Functions' }
How long the player's head should be forced to stay in its current direction.

### SetImmaculateConceptionState () {: aria-label='Functions' }
#### void SetImmaculateConceptionState ( int State ) {: .copyable aria-label='Functions' }
If you set a value that is greater than 14, the value is automatically capped at 14, meaning that the next heart picked up will spawn a familiar.
Note that the game checks to spawn a familiar only when the player picks up a heart, so you cannot trigger that directly with this function.
Sets how many hearts have been collected for the Immaculate Conception item.

### SetItemState () {: aria-label='Functions' }
#### void SetItemState ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
Changes the player's item state to the specified collectible. This is usually used for collectibles that the player holds above their head before activating (i.e: Bob's Rotten Head, Glass Cannon).

### SetKeepersSackBonus () {: aria-label='Functions' }
#### void SetKeepersSackBonus ( int Bonus ) {: .copyable aria-label='Functions' }
Sets the current coin bonus for the player's [Keeper's Sack](https://bindingofisaacrebirth.fandom.com/wiki/Keeper's_Sack) collectible.

### SetLaserColor () {: aria-label='Functions' }
#### void SetLaserColor ( [Color](Color.md) color ) {: .copyable aria-label='Functions' }
Sets the player's laser color.

### SetLuckModifier () {: aria-label='Functions' }
#### void SetLuckModifier ( int Modifier ) {: .copyable aria-label='Functions' }
Experimental Treatment adds `-1`, `0` or `1` depending on the luck rolled. Void may randomly add `1`.
The modifier is added directly to the player's Luck stat.
Used for Experimental Treatment and for stat boosts from Void.

### SetMaggySwingCooldown () {: aria-label='Functions' }
#### void SetMaggySwingCooldown ( int Cooldown ) {: .copyable aria-label='Functions' }
Sets the cooldown of Tainted Magdalene's swing attack to the specified amount of frames.

### SetMaxBladderCharge () {: aria-label='Functions' }
#### void SetMaxBladderCharge ( int Charge ) {: .copyable aria-label='Functions' }
Sets the maximum charge for when the player stops shooting and charges the Kidney Stone item.

### SetMegaBlastDuration () {: aria-label='Functions' }
#### void SetMegaBlastDuration ( int Duration ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
If the Mega Blast laser is active and you call the function again with a lower duration, the laser will persist even after the amount of frames has passed until the player leaves the room.
Sets the duration of the Mega Blast laser to the specified amount of frames. Setting the duration above zero will activate the effect if it wasn't already active.

### SetNextUrethraBlockFrame () {: aria-label='Functions' }
#### void SetNextUrethraBlockFrame ( int Frame ) {: .copyable aria-label='Functions' }
Sets the frame at which the player stops shooting and starts charging the Kidney Stone item.

### SetPonyCharge () {: aria-label='Functions' }
#### void SetPonyCharge ( int Time ) {: .copyable aria-label='Functions' }
Sets the duration of the charge effect from the A Pony and White Pony to the specified amount of frames.

### SetPoopSpell () {: aria-label='Functions' }
#### void SetPoopSpell ( int Slot, [PoopSpellType](https://wofsauge.github.io/IsaacDocs/rep/enums/PoopSpellType.html) PoopSpellType ) {: .copyable aria-label='Functions' }
Sets the specified slot in the poop list to a type of poop. This is only used by Tainted ???.

### SetPurityState () {: aria-label='Functions' }
#### void SetPurityState ( [PurityState](enums/PurityState.md) State ) {: .copyable aria-label='Functions' }
Set the state in which the [Purity](https://bindingofisaacrebirth.fandom.com/wiki/Purity) item effect currently is.

### SetRedStewBonusDuration () {: aria-label='Functions' }
#### void SetRedStewBonusDuration ( int Duration ) {: .copyable aria-label='Functions' }
Sets the duration of the damage bonus given by the Red Stew collectible to the specified amount of frames. Setting the duration above 0 will activate the effect if it wasn't active already.

### SetShotSpeedModifier () {: aria-label='Functions' }
#### void SetShotSpeedModifier ( int Modifier ) {: .copyable aria-label='Functions' }
Experimental Treatment adds `-1`, `0` or `1` depending on the shot speed rolled. Void may randomly add `1`.
Adds `0.2 * modifier` to the player's ShotSpeed.
Used for Experimental Treatment and for stat boosts from Void.

### SetSpeedModifier () {: aria-label='Functions' }
#### void SetSpeedModifier ( int Modifier ) {: .copyable aria-label='Functions' }
Adds `0.2 * modifier` to the player's MoveSpeed.
Experimental Treatment adds `-1`, `0` or `1` depending on the speed rolled. Void may randomly add `1`.
Used for Experimental Treatment and for stat boosts from Void.

### SetTearPoisonDamage () {: aria-label='Functions' }
#### void SetTearPoisonDamage ( float Damage ) {: .copyable aria-label='Functions' }

___
### SetTearRangeModifier () {: aria-label='Functions' }
#### void SetTearRangeModifier ( int Modifier ) {: .copyable aria-label='Functions' }
Adds `2.5 * modifier` to the player's TearRange.
Experimental Treatment adds `-1`, `0` or `1` depending on the range rolled. Void may randomly add `1`.
Used for Experimental Treatment and for stat boosts from Void.

### SetUrethraBlock () {: aria-label='Functions' }
#### void SetUrethraBlock ( boolean Blocked ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
Setting the `Blocked` argument to `false` seems to do nothing at all.
Sets whether the tear spam attack from the Kidney Stone collectible is about to activate. If the player does not have the Kidney Stone collectible, the effect is immediately activated.

### SetWeapon () {: aria-label='Functions' }
#### void SetWeapon ( [Weapon](Weapon.md) Weapon, int WeaponSlot ) {: .copyable aria-label='Functions' }
???- info "Info"
Always check for `nil`, even for slot `1` as it can be deleted by mods via [Isaac.DestroyWeapon()](Isaac.md#destroyweapon).
- `4` - Additional Weapon.
Weapon slots and their descriptions:
- `2` - Additional Weapon. Few instances of this exist in the vanilla game, but it can be populated by mods.
- `1` - Primary Weapon.
- `3` - Additional Weapon.
- `0` - Backup Weapon such as Notched Axe and Urn of Souls.
Sets the active Weapon in the assigned `WeaponSlot`.

### ShootBlueCandle () {: aria-label='Functions' }
#### void ShootBlueCandle ( [Vector](Vector.md) Direction ) {: .copyable aria-label='Functions' }
Makes the player shoot a blue flame from the Candle collectible.

### ShuffleCostumes () {: aria-label='Functions' }
#### void ShuffleCostumes ( int Seed = Random( ) ) {: .copyable aria-label='Functions' }
Randomizes the current costumes.

### SpawnAquariusCreep () {: aria-label='Functions' }
#### [EntityEffect](https://wofsauge.github.io/IsaacDocs/rep/EntityEffect.html) SpawnAquariusCreep ( [TearParams](https://wofsauge.github.io/IsaacDocs/rep/TearParams.html) TearParams = self.TearParams) {: .copyable aria-label='Functions' }
``player->GetTearHitParams(&params, WeaponType.WEAPON_TEARS, (*player->GetTearPoisonDamage() * 0.666f) / player->_damage, -(int)(-Isaac::Random(2) != 0) & 2 - 1, nil)``
???+ info "Info"
For reference, this is how the game calculates the `TearParams` for this normally:
Spawns a creep effect that acts like the ones created by Aquarius, including inhereting the player's `TearParams`. Supports passing a custom `TearParams` instead.

### SpawnClot () {: aria-label='Functions' }
#### void SpawnClot ( [Vector](Vector.md) pos, boolean AllowPlayerDeath = false ) {: .copyable aria-label='Functions' } 
Acts like a use of Sumptorium, removing health and spawning a clot with the type of health removed. If `AllowPlayerDeath` is set, a clot will spawn even if the health drained will kill the player.

### SpawnSaturnusTears () {: aria-label='Functions' }
#### int SpawnSaturnusTears ( ) {: .copyable aria-label='Functions' }
Spawns a ring of tears that orbit around the player akin to the Saturnus collectible.

### SwapForgottenForm () {: aria-label='Functions' }
#### void SwapForgottenForm ( boolean Force = false, boolean NoEffects = false) {: .copyable aria-label='Functions' }
If the player is The Forgotten/The Soul, the two will swap forms. Otherwise, this function does nothing.
`Force` will swap even if the subplayer doesn't have any health, or while a room/stage transition is active. `NoEffects` will disable the dust effect & fade from white when switching from The Soul to The Forgotten.

### SyncConsumableCounts () {: aria-label='Functions' }
#### void SyncConsumableCounts ( [EntityPlayer](EntityPlayer.md) Player, int CollectibleFlags ) {: .copyable aria-label='Functions' }      

___
### Teleport () {: aria-label='Functions' }
#### void Teleport ( [Vector](Vector.md) Position, boolean DoEffects = true, boolean TeleportTwinPlayers = false ) {: .copyable aria-label='Functions' }
`DoEffects` controls whether the teleport animation and sound plays. `TeleportTwinPlayers` controls whether twin players (e.g. Esau, Tainted Lazarus w/ Birthright) are teleported alongside this one.
Teleports the player to a position within the room.

### TriggerRoomClear () {: aria-label='Functions' }
#### void TriggerRoomClear ( ) {: .copyable aria-label='Functions' }
Triggers effects on the player as if a room was cleared (i.e. Charging actives).

### TryAddToBagOfCrafting () {: aria-label='Functions' }
#### void TryAddToBagOfCrafting ( [EntityPickup](EntityPickup.md) Pickup ) {: .copyable aria-label='Functions' }
Tries to add the specified pickup to the player's Bag of Crafting.

### TryDecreaseGlowingHourglassUses () {: aria-label='Functions' }
#### void TryDecreaseGlowingHourglassUses ( int Uses, boolean ForceHourglass = false ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
Attempts to decrease the uses left for the Glowing Hourglass collectible, if the player has it. `ForceHourglass` instantly removes all the charges and turns Glowing Hourglass into it's regular Hourglass form.
`Uses` are only decreased by 1 regardless of how large of a number you tell it to remove.

### TryFakeDeath () {: aria-label='Functions' }
#### boolean TryFakeDeath ( ) {: .copyable aria-label='Functions' }
Spawns a copy of the player at its current position and plays the death animation and sound.

### TryForgottenThrow () {: aria-label='Functions' }
#### boolean TryForgottenThrow ( [Vector](Vector.md) Direction ) {: .copyable aria-label='Functions' }
If the player is holding Tainted Forgotten, he is thrown towards the specified direction.

### TryPreventDeath () {: aria-label='Functions' }
#### boolean TryPreventDeath ( ) {: .copyable aria-label='Functions' }
Returns `true` on success, otherwise `false`.
Adds a heart container to a character if there are none left to prevent death, depending on its [HealthType](enums/HealthType.md).

### TryRemoveSmeltedTrinket () {: aria-label='Functions' }
#### void TryRemoveSmeltedTrinket ( [TrinketType](https://wofsauge.github.io/IsaacDocs/rep/enums/TrinketType.html) ID ) {: .copyable aria-label='Functions' }    
Tries to remove the specified smelted trinket from the player.

### UnblockCollectible () {: aria-label='Functions' }
#### void UnblockCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
Unblocks the [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) that was blocked through [BlockCollectible](EntityPlayer.md#blockcollectible).

### UpdateIsaacPregnancy () {: aria-label='Functions' }
#### void UpdateIsaacPregnancy ( boolean UpdateCambion ) {: .copyable aria-label='Functions' }
Set `true` if you want to update the [Cambion Conception](https://bindingofisaacrebirth.fandom.com/wiki/Cambion_Conception) costume, otherwise updates the [Immaculate Conception](https://bindingofisaacrebirth.fandom.com/wiki/Immaculate_Conception) costume.

### VoidHasCollectible () {: aria-label='Functions' }
#### boolean VoidHasCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
Returns true if the specified collectible has been consumed by the Void collectible.
