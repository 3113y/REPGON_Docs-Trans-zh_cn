---
tags:
  - Class
---
# Class "ItemPool"

## Modified Functions

### GetCollectible () {: aria-label='Modified Functions' }
#### [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) GetCollectible ( [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) PoolType, boolean Decrease = false, int Seed = Random(), [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) DefaultItem = CollectibleType.COLLECTIBLE_NULL, [GetCollectibleFlag](enums/GetCollectibleFlag.md) Flags = 0 ) {: .copyable aria-label='Modified Functions' }
???+ warning "Setting both Ban Flags"
Now gives access to the Flags parameter.
Setting both the `BAN_ACTIVE` and the `BAN_PASSIVE` flag will cause the function to always return either the `DefaultItem` or `CollectibleType.COLLECTIBLE_BREAKFAST`

### AddBibleUpgrade () {: aria-label='Functions' }
#### void AddBibleUpgrade ( int Add, [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) PoolType ) {: .copyable aria-label='Functions' }

___
### CanSpawnCollectible () {: aria-label='Functions' }
#### boolean CanSpawnCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible, boolean ignoreLocked ) {: .copyable aria-label='Functions' }
???+ info "IgnoreLocked"
If `IgnoreLocked` is set to true, this function will return true for items that could appear but are locked behind achievements.
It will still return false if the item was removed from the item pool or if it can't appear because other effects (Tainted Lost offensive items mechanic or NO! trinket effect).

### GetBibleUpgrades () {: aria-label='Functions' }
#### int GetBibleUpgrades ( [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) PoolType ) {: .copyable aria-label='Functions' }
Returns number of Bible collectibles added to a pool.

### GetCardEx () {: aria-label='Functions' }
#### [Card](https://wofsauge.github.io/IsaacDocs/rep/enums/Card.html) GetCardEx ( int Seed, int SpecialChance, int RuneChance, int SuitChance, boolean AllowNonCards ) {: .copyable aria-label='Functions' }
More sophisticated version of [ItemPool:GetCard()](https://wofsauge.github.io/IsaacDocs/rep/ItemPool.html#getcard) that allows to define individual chances.

### GetCollectibleFromList () {: aria-label='Functions' }
#### [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) GetCollectibleFromList ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html)[] ItemList, int Seed = Random(), [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) DefaultItem = CollectibleType.COLLECTIBLE_BREAKFAST, boolean AddToBlacklist = true, boolean ExcludeLockedItems = false ) {: .copyable aria-label='Functions' }

___
### GetCollectiblesFromPool () {: aria-label='Functions' }
#### table GetCollectiblesFromPool ( [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) PoolType ) {: .copyable aria-label='Functions' }
| initialWeight | float | |
|:--|:--|:--|
| isUnlocked | boolean | |
Returns a table of collectibles registered in the specified pool. The table contains the following fields
|Field|Type|Comment|
| weight | float | |
| removeOn | float | |
| decreaseBy | float | |
| itemID | [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) | |

### GetNumAvailableTrinkets () {: aria-label='Functions' }
#### int GetNumAvailableTrinkets ( ) {: .copyable aria-label='Functions' }
Returns the amount of trinkets available in the item pool.

### GetNumItemPools () {: aria-label='Functions' }
#### int GetNumItemPools ( ) {: .copyable aria-label='Functions' }
Retrieves the total number of item pools in the game, including custom item pools.

### GetPillColor () {: aria-label='Functions' }
#### [PillColor](https://wofsauge.github.io/IsaacDocs/rep/enums/PillColor.html) GetPillColor ( [PillEffect](https://wofsauge.github.io/IsaacDocs/rep/enums/PillEffect.html) ID ) {: .copyable aria-label='Functions' }
Currently not applied by pill modifications, such as PHD/False PHD.
Returns a PillColor matching the specificed PillEffect, returns -1 if the Effect is not in the rotation.

### GetRandomPool () {: aria-label='Functions' }
#### [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) GetRandomPool ( [RNG](RNG.md) RNG, boolean AdvancedSearch = false, [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html)[] Filter = {}, boolean IsWhitelist = false) {: .copyable aria-label='Functions' }
table.insert(CustomPools, i)
local CustomPools = {}
Normally this function is tied to the same rules as Chaos, meaning that you can only get the pools for the current mode, but by setting `Advanced Search` to true you can bypass these restrictions.
local PoolList = {
ItemPoolType.POOL_ROTTEN_BEGGAR
local rng = RNG(Random()) -- replace this with your own rng
```lua
???+ example "Pick Pool From Vanilla"
ItemPoolType.POOL_BATTERY_BUM,
-- Put all custom pools within the Filter
local randomPool = Game():GetItemPool():GetRandomPool(rng, true, CustomPools, false)
ItemPoolType.POOL_DEMON_BEGGAR,
Setting `Advanced Search` to true allows you to make use of the `Filter` parameter.
local rng = RNG() -- replace this with your own rng
local randomPool = Game():GetItemPool():GetRandomPool(rng, true, PoolList, true)
This code picks a random pool from any of the "Beggar" pools
Picks a random pool in an identical manner to Chaos, where pools with more items have a higher probability of being chosen compared to those with fewer items.
ItemPoolType.POOL_BOMB_BUM,
Normally the `Filter` acts as a blacklist of unwanted itemPools, however setting `IsWhitelist` to true turns it into a list from which to choose from.
for i = 31, itemPool:GetNumItemPools() - 1 do
end
???+ info "Advanced Search"
local itemPool = Game():GetItemPool()
ItemPoolType.POOL_KEY_MASTER,
ItemPoolType.POOL_BEGGAR,
This code picks a random pool from any of the vanilla
???+ example "Pick Pool From List"
}
```

### GetRemovedCollectibles () {: aria-label='Functions' }
#### table GetRemovedCollectibles ( ) {: .copyable aria-label='Functions' }
local removedCollectibles = itemPool:GetRemovedCollectibles()
Returns a table of [collectibles](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) removed from all pools.
if removedCollectibles[CollectibleType.COLLECTIBLE_SAD_ONION] then
end
```lua
```
print("Sad onion removed!")
???- example "Example Code"
This code checks if the sad onion has been removed.

### GetRoomBlacklistedCollectibles () {: aria-label='Functions' }
#### table GetRoomBlacklistedCollectibles ( ) {: .copyable aria-label='Functions' }
print("Sad onion blacklisted!")
Returns a table of [collectibles](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) blacklisted in the current room.
local blacklistedCollectibles = itemPool:GetRoomBlacklistedCollectibles()
end
```lua
```
???- example "Example Code"
This code checks if the sad onion has been removed.
if blacklistedCollectibles[CollectibleType.COLLECTIBLE_SAD_ONION] then

### HasCollectible () {: aria-label='Functions' }
#### boolean HasCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
Returns `true` if collectible is available in item pools, `false` otherwise.

### HasTrinket () {: aria-label='Functions' }
#### boolean HasTrinket ( [TrinketType](https://wofsauge.github.io/IsaacDocs/rep/enums/TrinketType.html) Trinket ) {: .copyable aria-label='Functions' }
Returns `true` if trinket is currently available in trinket pool, `false` otherwise.

### PickCollectible () {: aria-label='Functions' }
#### table PickCollectible ( [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) PoolType, boolean Decrease = false, [RNG](RNG.md) RNG = RNG(), [GetCollectibleFlag](enums/GetCollectibleFlag.md) Flags = 0 ) {: .copyable aria-label='Functions' }
| initialWeight | float | |
| weight | float | |
- Does not attempt to morph the collectible into `CollectibleType.COLLECTIBLE_BIBLE`, `CollectibleType.COLLECTIBLE_MAGIC_SKIN` or `CollectibleType.COLLECTIBLE_ROSARY`
- Does not generate a [Glitched Item](ProceduralItem.md) when having the `CollectibleType.COLLECTIBLE_TMTRAINER` effect.
???+ info "Differences with GetCollectible"
If RNG is not set, its initialized with `RNG(Random(), 4)`
Returns the raw result of [GetCollectible()](ItemPool.md#getcollectible), without any of the filtering applied by the original function.
If the pool has completely ran out of repicks then this function will return `nil`.
For reference GetCollectible() **Gives Up** after either this function has failed to pick an Unlocked collectible 20 times in a row or has failed to produce any result at all (nil).
| decreaseBy | float | |
|:--|:--|:--|
| isUnlocked | boolean | |
- Does not randomize the pool when having the `CollectibleType.COLLECTIBLE_CHAOS` effect.
- Does not trigger the [MC_PRE_GET_COLLECTIBLE](https://wofsauge.github.io/IsaacDocs/rep/enums/ModCallbacks.html?h=modcall#mc_post_get_collectible) and [MC_POST_GET_COLLECTIBLE](https://wofsauge.github.io/IsaacDocs/rep/enums/ModCallbacks.html?h=modcall#mc_post_get_collectible) callback.
The table contains the following fields:
| removeOn | float | |
|Field|Type|Comment|
- Does not attempt to get a collectible from `ItemPoolType.POOL_TREASURE` if **Giving up**.
- Does not morph the collectible into `CollectibleType.COLLECTIBLE_BREAKFAST` if **Giving up**.
| itemID | [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) | |

### ResetCollectible () {: aria-label='Functions' }
#### void ResetCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
Makes the available once again, allowing it to naturally spawned even if previously remove. Also restores all instances of the collectible to it's **initialWeight** in every item pool.

### SetLastPool () {: aria-label='Functions' }
#### void SetLastPool ( [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) ) {: .copyable aria-label='Functions' }

___
### UnidentifyPill () {: aria-label='Functions' }
#### void UnidentifyPill ( [PillColor](https://wofsauge.github.io/IsaacDocs/rep/enums/PillColor.html) Pill ) {: .copyable aria-label='Functions' }
Will reset a pill back to unidentified (???) state.
