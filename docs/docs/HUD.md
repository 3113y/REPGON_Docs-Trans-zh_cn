---
tags:
  - Class
---
# Class "HUD"

???+ info

    你可以通过以下函数获取此类:

    * [Game:GetHUD()](https://wofsauge.github.io/IsaacDocs/rep/Game.html#gethud)
    
    ???+ example "Example Code"

        ```lua
        local hud = Game():GetHUD()
        local sprite = hud:GetChargeBarSprite()
        ```

## Functions

### FlashRedHearts () {: aria-label='Functions' }
#### void FlashRedHearts ( [EntityPlayer](EntityPlayer.md) Player ) {: .copyable aria-label='Functions' }

___
### GetBossHPBarFill () {: aria-label='Functions' }
#### float GetBossHPBarFill ( ) {: .copyable aria-label='Functions' }
获取boss血条的填充量

___
### GetCardsPillsSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetCardsPillsSprite ( ) {: .copyable aria-label='Functions' }
用于在HUD中渲染药丸、卡牌和符文图标的精灵对象。

___
### GetChargeBarSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetChargeBarSprite ( ) {: .copyable aria-label='Functions' }

___
### GetCoopMenuSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetCoopMenuSprite ( ) {: .copyable aria-label='Functions' }
用于渲染合作玩家选择菜单的精灵对象。

___
### GetCraftingSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetCraftingSprite ( ) {: .copyable aria-label='Functions' }
用于制作物品栏HUD的精灵对象。

___
### GetFortuneSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetFortuneSprite ( ) {: .copyable aria-label='Functions' }
用于幸运弹窗窗口的精灵对象。

___
### GetHeartsSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetHeartsSprite ( ) {: .copyable aria-label='Functions' }

___
### GetInventorySprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetInventorySprite ( ) {: .copyable aria-label='Functions' }
用于堕化以撒的物品栏系统的精灵对象。

___
### GetPickupsHUDSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetPickupsHUDSprite ( ) {: .copyable aria-label='Functions' }

___
### GetPlayerHUD () {: aria-label='Functions' }
#### [PlayerHUD](PlayerHUD.md) GetPlayerHUD ( int Index = 0 ) {: .copyable aria-label='Functions' }

___
### GetPoopSpellSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetPoopSpellSprite ( ) {: .copyable aria-label='Functions' }
堕化？？？的便便副主动的精灵对象

___
### GetStreakSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetStreakSprite ( ) {: .copyable aria-label='Functions' }
用于文本连击弹出窗口的精灵对象。例如：拾取物品、显示楼层名称等。

___
### SetBossHPBarFill () {: aria-label='Functions' }
#### void SetBossHPBarFill ( float percent ) {: .copyable aria-label='Functions' }
设置boss血条的填充量。接受0到1之间的值。小于0的数字会导致boss血条不被渲染。

___