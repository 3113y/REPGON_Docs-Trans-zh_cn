---
tags:
  - Global
  - Class
---
# Global Class "ItemOverlay"

???+ info
    You can get this class by using the `ItemOverlay` global table.
    
    **注意：调用这些函数时，必须使用 .（句点）而非 :（冒号）！**
    
    ???+ example "Example Code"
        ```lua
        local overlaysprite = ItemOverlay.GetSprite()
        ```
        
## Functions

### GetDelay () {: aria-label='Functions' }
#### int GetDelay ( ) {: .copyable aria-label='Functions' }

___
### GetMegaMushPlayerSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetMegaMushPlayerSprite ( ) {: .copyable aria-label='Functions' } 

___
### GetOverlayID () {: aria-label='Functions' }
#### [Giantbook](enums/Giantbook.md) GetOverlayID ( ) {: .copyable aria-label='Functions' }
???+ info "Info"
If none have played yet, returns 0.
Returns the last Giantbook animation that played. This is the current Giantbook if one is currently playing.
### GetPlayer () {: aria-label='Functions' }
#### [EntityPlayer](EntityPlayer.md) GetPlayer ( ) {: .copyable aria-label='Functions' }

___
### GetSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetSprite ( ) {: .copyable aria-label='Functions' }

___
### Show () {: aria-label='Functions' }
#### void Show ( [Giantbook](enums/Giantbook.md) GiantbookID, int Delay = 3, [EntityPlayer](EntityPlayer.md) = nil ) {: .copyable aria-label='Functions' }

___
