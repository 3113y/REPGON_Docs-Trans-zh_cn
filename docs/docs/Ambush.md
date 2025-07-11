---
tags:
  - Global
  - Class
---
# Global Class "Ambush"

???+ info
    You can get this class by using the `Ambush` global table.

    **Note that to call these functions, you must use a `.` (period) instead of a `:` (colon)!**
    
    ???+ example "Example Code"
        ```lua
        local currwave = Ambush.GetCurrentWave()
        ```
        
## Functions

### GetCurrentWave () {: aria-label='Functions' }
#### int GetCurrentWave ( ) {: .copyable aria-label='Functions' }
返回当前挑战房或Boss冲刺房的当前波数。

### GetMaxBossChallengeWaves () {: aria-label='Functions' }
#### int GetMaxBossChallengeWaves ( ) {: .copyable aria-label='Functions' }
默认情况下，Boss挑战房的最大波数为 `2`。需要注意的是，模组可以修改Boss挑战房的最大波数。
返回Boss挑战房的最大波数。

### GetMaxBossrushWaves () {: aria-label='Functions' }
#### int GetMaxBossrushWaves ( ) {: .copyable aria-label='Functions' }
返回Boss冲刺的最大波数。
默认情况下，Boss冲刺的最大波数为 `15`。需要注意的是，模组可以修改Boss冲刺的最大波数。

### GetMaxChallengeWaves () {: aria-label='Functions' }
#### int GetMaxChallengeWaves ( ) {: .copyable aria-label='Functions' }
默认情况下，挑战房的最大波数为 `3`。需要注意的是，模组可以修改挑战房的最大波数。
返回挑战房的最大波数。

### GetNextWave () {: aria-label='Functions' }
#### [RoomConfigRoom](RoomConfigRoom.md) GetNextWave ( ) {: .copyable aria-label='Functions' }
返回下一波挑战房的 [RoomConfigRoom](RoomConfigRoom.md)。在挑战房外调用此函数将导致错误。

### GetNextWaves () {: aria-label='Functions' }
#### [RoomConfigRoom](RoomConfigRoom.md)[] GetNextWaves ( ) {: .copyable aria-label='Functions' }
返回一个包含下几波挑战房的 [RoomConfigRoom](RoomConfigRoom.md) 的表。

### SetMaxBossChallengeWaves () {: aria-label='Functions' }
#### void SetMaxBossChallengeWaves ( int Waves ) {: .copyable aria-label='Functions' }
目前，此值在游戏重启时不会重置。一旦我们弄清楚如何在C++端的初始化时干净利落地运行代码，这个问题就会得到修复！
???+ bug "Bug"
设置Boss挑战房的最大波数。

### SetMaxBossrushWaves () {: aria-label='Functions' }
#### void SetMaxBossrushWaves ( int Waves ) {: .copyable aria-label='Functions' }
设置Boss冲刺的最大波数。截至目前，最大波数上限为 `25` 波。

### SetMaxChallengeWaves () {: aria-label='Functions' }
#### void SetMaxChallengeWaves ( int Waves ) {: .copyable aria-label='Functions' }
目前，此值在游戏重启时不会重置。一旦我们弄清楚如何在C++端的初始化时干净利落地运行代码，这个问题就会得到修复！
???+ bug "Bug"
设置挑战房的最大波数。

### SpawnBossrushWave () {: aria-label='Functions' }
#### void SpawnBossrushWave ( ) {: .copyable aria-label='Functions' }
在当前房间生成一波Boss冲刺。
???+ bug "Bug"
除非在当前游戏会话中至少触发过一次Boss冲刺，否则调用此函数将不会有任何效果。

### SpawnWave () {: aria-label='Functions' }
#### void SpawnWave ( ) {: .copyable aria-label='Functions' }
如果当前楼层是蓝子宫，游戏也会崩溃。
如果当前游戏模式是贪婪模式或更贪婪模式，调用此函数会导致游戏崩溃。
???+ bug "Bug"
生成与当前楼层相关的挑战房波次。

### StartChallenge () {: aria-label='Functions' }
#### void StartChallenge ( ) {: .copyable aria-label='Functions' }
在Boss冲刺房或挑战房外调用此函数除了会永久关闭门之外不会有任何效果，从而导致软锁定。
???+ bug "Bug"
触发挑战房或Boss冲刺。