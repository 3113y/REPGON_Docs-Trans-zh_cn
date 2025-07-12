---
tags:
  - Class
---
# Class "Game"

## Modified Functions


### GetLastDevilRoomStage () {: aria-label='Modified Functions' }
#### [LevelStage](https://wofsauge.github.io/IsaacDocs/rep/enums/LevelStage.html) GetLastDevilRoomStage ( ) {: .copyable aria-label='Modified Functions' }
现在返回整数，而非无法使用的用户数据。

### GetLastLevelWithDamage () {: aria-label='Modified Functions' }
#### [LevelStage](https://wofsauge.github.io/IsaacDocs/rep/enums/LevelStage.html) GetLastLevelWithDamage ( ) {: .copyable aria-label='Modified Functions' }
现在返回整数，而非无法使用的用户数据。

### GetLastLevelWithoutHalfHp () {: aria-label='Modified Functions' }
#### [LevelStage](https://wofsauge.github.io/IsaacDocs/rep/enums/LevelStage.html) GetLastLevelWithoutHalfHp ( ) {: .copyable aria-label='Modified Functions' }
现在返回整数，而非无法使用的用户数据。

### GetPlayer ()  {: aria-label='Modified Functions' }
#### [EntityPlayer](EntityPlayer.md) GetPlayer ( int Index ) {: .copyable aria-label='Modified Functions' }
如果不存在玩家，现在将返回 `nil` 以防止崩溃。无效的索引将返回索引 `0`。

### Move·To·Random·Room () {: aria-label='Modified Functions' }
#### void MoveToRandomRoom ( boolean IAmErrorRoom, int Seed, [EntityPlayer](EntityPlayer.md) Player ) {: .copyable aria-label='Modified Functions' }
Now no longer crashes the game when given a seed equal `0`.
___
### StartStageTransition ()  {: aria-label='Modified Functions' }
#### void StartStageTransition ( boolean SameStage, int TransitionOverride, [EntityPlayer](EntityPlayer.md) Player = nil ) {: .copyable aria-label='Modified Functions' }
`Player` 现在是可选的（将默认使用 `GetPlayer(0)`）。
修复了有时由于 C++ 端调用不正确而导致的崩溃问题。

### AchievementUnlocksDisallowed () {: aria-label='Functions' }
#### boolean AchievementUnlocksDisallowed ( ) {: .copyable aria-label='Functions' }
如果本次游戏流程中无法解锁成就（如挑战模式、有种子的游戏等），则返回 `true`。

### AddDebugFlags () {: aria-label='Functions' }
#### void AddDebugFlags ( [DebugFlag](enums/DebugFlag.md) Flag ) {: .copyable aria-label='Functions' }
向游戏中添加调试标志。可以使用按位连接同时添加多个标志（例如 `DebugFlag.ENTITY_POSITIONS | DebugFlag.HITSPHERES`）。

### AddShopVisits () {: aria-label='Functions' }
#### void AddShopVisits ( int Count ) {: .copyable aria-label='Functions' }
增加玩家在本次游戏流程中进入商店的次数。

### ClearErasedEnemies () {: aria-label='Functions' }
#### void ClearErasedEnemies ( ) {: .copyable aria-label='Functions' }
清除所有被标记为已清除的敌人，使它们能够再次生成。

### DevolveEnemy () {: aria-label='Functions' }
#### void DevolveEnemy ( [Entity](Entity.md) ) {: .copyable aria-label='Functions' }
使敌人退化，就好像使用了道具 D10 一样。

### GetChallengeParams () {: aria-label='Functions' }
#### [ChallengeParam](ChallengeParam.md) GetChallengeParams ( ) {: .copyable aria-label='Functions' }

___
### GetCurrentColorModifier () {: aria-label='Functions' }
#### [ColorModifier](ColorModifier.md) GetCurrentColorModifier ( ) {: .copyable aria-label='Functions' }
获取《忏悔》中引入的颜色校正的副本。这存储的是当前正在使用的原始值（可能会受到诸如“星体投射”等道具的影响），而不是房间设置使用的值（有关此内容，请参阅 [FXParams.ColorModifier](FXParams.md#colormodifier)）。

### GetDebugFlags () {: aria-label='Functions' }
#### int GetDebugFlags ( ) {: .copyable aria-label='Functions' }
返回一个 [DebugFlag](enums/DebugFlag.md) 位掩码。

### GetDizzyAmount () {: aria-label='Functions' }
#### float GetDizzyAmount ( ) {: .copyable aria-label='Functions' }
返回当前类似于“波浪帽”的眩晕程度。

### GetGenericPrompt () {: aria-label='Functions' }
#### [GenericPrompt](GenericPrompt.md) GetGenericPrompt ( ) {: .copyable aria-label='Functions' }
返回当前活动的 `GenericPrompt` 对象。
???+ bug "Bug"
在游戏流程中且没有活动提示时使用此函数会导致游戏崩溃。

### GetLerpColorModifier () {: aria-label='Functions' }
#### [ColorModifier](ColorModifier.md) GetLerpColorModifier ( ) {: .copyable aria-label='Functions' }
返回插值颜色校正器。其格式为绝对变化率（即，所有值都是正数）。

### GetPauseMenuState () {: aria-label='Functions' }
#### [PauseMenuStates](enums/PauseMenuStates.md) GetPauseMenuState ( ) {: .copyable aria-label='Functions' }

___
### GetPlanetariumsVisited () {: aria-label='Functions' }
#### int GetPlanetariumsVisited ( ) {: .copyable aria-label='Functions' }
返回玩家在本次游戏流程中进入天文馆的次数。

### GetShopVisits () {: aria-label='Functions' }
#### int GetShopVisits ( ) {: .copyable aria-label='Functions' }
返回玩家在本次游戏流程中进入商店的次数。

### GetTargetColorModifier () {: aria-label='Functions' }
#### [ColorModifier](ColorModifier.md) GetTargetColorModifier ( ) {: .copyable aria-label='Functions' }
返回目标颜色校正器。如果当前正在两个 [ColorModifier](ColorModifier.md) 状态之间进行插值，则返回目标状态。否则，它与 [GetCurrentColorModifier](Game.md#getcurrentcolormodifier) 相同。

### IsErased () {: aria-label='Functions' }
#### boolean IsErased ( [Entity](Entity.md) Entity ) {: .copyable aria-label='Functions' }
检查一个实体是否已被清除。

### IsGreedBoss () {: aria-label='Functions' }
#### boolean IsGreedBoss ( ) {: .copyable aria-label='Functions' }
如果下一波或当前波是 boss 波，则返回 `true`。否则返回 `false`，如果不在贪婪模式下也返回 `false`。

### IsGreedFinalBoss () {: aria-label='Functions' }
#### boolean IsGreedFinalBoss ( ) {: .copyable aria-label='Functions' }
如果下一波或当前波是可选的“噩梦”波，则返回 `true`。否则返回 `false`，如果不在贪婪模式下也返回 `false`。

### IsHardMode () {: aria-label='Functions' }
#### boolean IsHardMode ( ) {: .copyable aria-label='Functions' }
如果当前模式是困难模式或贪婪ier模式，则返回 `true`。

### IsPauseMenuOpen () {: aria-label='Functions' }
#### boolean IsPauseMenuOpen ( ) {: .copyable aria-label='Functions' }
如果暂停菜单已打开，则返回 `true`。

### IsRerun () {: aria-label='Functions' }
#### boolean IsRerun ( ) {: .copyable aria-label='Functions' }
如果当前游戏流程是重玩，则返回 `true`。

### RecordPlayerCompletion () {: aria-label='Functions' }
#### void RecordPlayerCompletion ( [CompletionType](enums/CompletionType.md) Type ) {: .copyable aria-label='Functions' }
为所有玩家设置与该类型相关的标记并解锁成就。游戏使用此函数来授予标记以及受污染的完成纸组。

### SetBloom () {: aria-label='Functions' }
#### void SetBloom ( float Duration, float Amount ) {: .copyable aria-label='Functions' }

___
### SetColorModifier () {: aria-label='Functions' }
#### void SetColorModifier ( [ColorModifier](ColorModifier.md) ColorModifier, boolean Lerp = true, float Rate = 0.015 ) {: .copyable aria-label='Functions' }

___
### SetDizzyAmount () {: aria-label='Functions' }
#### void SetDizzyAmount ( float TargetIntensity , float CurrentIntensity ) {: .copyable aria-label='Functions' }
使用此函数时，最好将值保持在 `0` - `1` 之间，并以 0.1 为增量进行调整。`1` 对屏幕的影响最极端，而 `0` 则移除该效果。
效果的当前强度将逐渐向“目标强度”移动。
???+ warning "Warning"
向此函数提供“当前强度”是可选的。如果提供了该值，当前强度将立即更改为该值。如果未指定，则当前强度将保持不变。
设置类似于“波浪帽”的眩晕程度。### SetDonationModAngel () {: aria-label='Functions' }
#### void SetDonationModAngel ( int Amount ) {: .copyable aria-label='Functions' }

___
### SetDonationModGreed () {: aria-label='Functions' }
#### void SetDonationModGreed ( int Amount ) {: .copyable aria-label='Functions' }

___
### ShowGenericLeaderboard () {: aria-label='Functions' }
#### void ShowGenericLeaderboard ( ) {: .copyable aria-label='Functions' }

___
### SpawnBombCrater () {: aria-label='Functions' }
#### [Entity](Entity.md) SpawnBombCrater ( [Vector](Vector.md) Position, float Radius = 1.0 ) {: .copyable aria-label='Functions' }

___