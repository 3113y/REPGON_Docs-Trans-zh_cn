---
tags:
  - Class
---
# Class "EntitySlot"

It's Real.

## Class Diagram
--8<-- "docs/snippets/EntityClassDiagram_NewFunkyMode.md"
## Functions

### CreateDropsFromExplosion () {: aria-label='Functions' }
#### void CreateDropsFromExplosion ( ) {: .copyable aria-label='Functions' }
这会强制实体插槽（EntitySlot）掉落其在被炸时通常会掉落的物品。

### GetDonationValue () {: aria-label='Functions' }
#### int GetDonationValue ( ) {: .copyable aria-label='Functions' }
- 恶魔乞丐：已捐赠的红心数量。
???- info "返回信息"
返回给予乞丐的硬币数量。返回的数字会根据乞丐的不同而有所变化。
- 普通乞丐：已捐赠的硬币数量。
- 电池流浪汉、腐烂乞丐：每次支付时随机增加，最多增加到3，在给予奖励或支付报酬后重置为0。
- 所有其他插槽：保持为0。

### GetPrizeCollectible () {: aria-label='Functions' }
#### [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) GetPrizeCollectible ( ) {: .copyable aria-label='Functions' }
似乎仅由抓娃娃机和地狱游戏使用。获取获胜时作为奖品颁发的收藏品。

### GetPrizeType () {: aria-label='Functions' }
#### int GetPrizeType ( ) {: .copyable aria-label='Functions' }
- 老虎机：返回一个介于`3` - `24`之间的数字。`3` - `12`会使机器吐出奖励。
???- info "返回信息"
- `3`：苍蝇或漂亮苍蝇。
- `10` - `12`：1 - 2枚硬币。
- 炸弹流浪汉：根据其输出的奖品类型返回一个介于`1` - `3`之间的数字。
- `1`：硬币。
- `3`：收藏品。
- `5` - `6`：红心。
- `13` - `24`：无奖励。
- 贝壳游戏和地狱游戏：返回潜在奖品的`拾取物变体（PickupVariant）`。
- `4`：炸弹。
- `2`：红心。
- `7`：钥匙。
- `9`：未知。此值似乎从未被使用过。
- `8`：药丸。
返回一个根据老虎机不同而变化的整数。

### GetShellGameAnimationIndex () {: aria-label='Functions' }
#### int GetShellGameAnimationIndex ( ) {: .copyable aria-label='Functions' }
返回贝壳游戏和地狱游戏用于确定播放哪个奖品动画的索引。

### GetState () {: aria-label='Functions' }
#### int GetState ( ) {: .copyable aria-label='Functions' }
- `4`：支付报酬
- `2`：奖励（贝壳游戏和地狱游戏：闲置奖励状态）
- `5`：奖励（仅适用于贝壳游戏和地狱游戏）
- `3`：被炸
- `1`：闲置。
返回插槽的当前状态。
所有插槽都有一个基于其当前行为的一致状态，具体如下：
???+ info "返回信息"

### GetTimeout () {: aria-label='Functions' }
#### int GetTimeout ( ) {: .copyable aria-label='Functions' }
???- info "返回信息"
- 抓娃娃机：第一次成功支付报酬时，最小超时时间为`1 << 16`，仍会增加30并开始倒计时。第二次支付报酬时为`1 << 17`。第三次支付报酬时为`1 << 16` + `1 << 17`。
返回插槽确定其奖品之前的超时帧数。并非所有插槽都会使用此功能。
- 所有其他插槽：保持为0。
- 除炸弹乞丐外的所有乞丐：每次支付时随机增加，返回`1 << 16`、`1 << 17`或它们的和，在给予奖励后重置为0。

### GetTouch () {: aria-label='Functions' }
#### int GetTouch ( ) {: .copyable aria-label='Functions' }
返回插槽的触摸计数器。当玩家触摸插槽时，触摸计数器每帧增加1，当没有玩家触摸时重置。

### GetTriggerTimerNum () {: aria-label='Functions' }
#### int GetTriggerTimerNum ( ) {: .copyable aria-label='Functions' }
重铸机每次成功重铸时将此值增加`1`。被炸时，有机会将其设置为11并重新生成另一个物品。
轰炸炸弹流浪汉时，此值会被设置为`30`。
???+ note "返回信息"
返回炸弹流浪汉和重铸机使用的一个数字。

### RandomCoinJamAnim () {: aria-label='Functions' }
#### string RandomCoinJamAnim ( ) {: .copyable aria-label='Functions' }
从以下选项中返回一个随机字符串：`CoinJam`、`CoinJam2`、`CoinJam3`、`CoinJam4`。推测仅用于捐赠机器。

### SetDonationValue () {: aria-label='Functions' }
#### void SetDonationValue ( int DonationValue ) {: .copyable aria-label='Functions' }
设置插槽的捐赠值。更多信息请参阅[GetDonationValue](EntitySlot.md#getdonationvalue)。

### SetPrizeCollectible () {: aria-label='Functions' }
#### void SetPrizeCollectible ( [CollectibleType](https://wofsauge.github.io/IsaacDocs/rep/enums/CollectibleType.html) Collectible ) {: .copyable aria-label='Functions' }
似乎仅由抓娃娃机和地狱游戏使用。此函数设置游戏将支付的收藏品，并相应地更新渲染的收藏品。

### SetPrizeType () {: aria-label='Functions' }
#### void SetPrizeType ( int PrizeType ) {: .copyable aria-label='Functions' }
设置插槽的奖品类型。更多信息请参阅[GetPrizeType](EntitySlot.md#getprizetype)。

### SetShellGameAnimationIndex () {: aria-label='Functions' }
#### void SetShellGameAnimationIndex ( int index ) {: .copyable aria-label='Functions' }
设置贝壳游戏和地狱游戏用于确定播放哪个奖品动画的索引。

### SetState () {: aria-label='Functions' }
#### void SetState ( int State ) {: .copyable aria-label='Functions' }
设置插槽的状态。更多信息请参阅[GetState](EntitySlot.md#getstate)。

### SetTimeout () {: aria-label='Functions' }
#### void SetTimeout ( int Timeout ) {: .copyable aria-label='Functions' }
设置插槽的超时时间。更多信息请参阅[GetTimeout](EntitySlot.md#gettimeout)。

### SetTouch () {: aria-label='Functions' }
#### void SetTouch ( int Touch ) {: .copyable aria-label='Functions' }
设置插槽的触摸计数器。当玩家触摸插槽时，触摸计数器每帧增加1，当没有玩家触摸时重置为0。

### SetTriggerTimerNum () {: aria-label='Functions' }
#### void SetTriggerTimerNum ( int num ) {: .copyable aria-label='Functions' }
???+ note "更多信息"
重铸机每次成功重铸时将此值增加`1`。被炸时，有机会将其设置为11并重新生成另一个物品。
轰炸炸弹流浪汉时，此值会被设置为`30`。
返回炸弹流浪汉和重铸机使用的一个数字。