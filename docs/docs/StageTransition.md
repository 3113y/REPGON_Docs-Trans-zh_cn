---
tags:
  - Global
  - Class
---
# Global Class "StageTransition"

???+ info
    This class gives access to data exclusive to the stage transition screen.
    
    Please note that the `StageTransition` is only used to configure how the stage transition plays. If you want to manipulate the content of the screen during a stage transition, you need to use the NightmareScene class.
    
    You can get this class by using the `StageTransition` global table.
    
    **注意：调用这些函数时，必须使用 .（句点）而非 :（冒号）！**
    
    ???+ example "Example Code"
        ```lua
        local samestage = StageTransition.GetSameStage()
        ```


## Functions 

### GetSameStage () {: aria-label='Functions' }
#### boolean GetSameStage ( ) {: .copyable aria-label='Functions' }
Indicate if the stage transition screen will display Isaac's head moving from one stage to the other (`false`) or not (`true`).

### SetSameStage () {: aria-label='Functions' }
#### void SetSameStage ( boolean Value ) {: .copyable aria-label='Functions' }
Calling this method before the current stage transition has called `SetNextStage` will override the transition itself. This means that instead of merely displaying Isaac's head not moving, it will actually change whether the next stage will be a repeat of the current one, or the actual next stage. Ideally, you should use this function in the context of the `ModCallbacks.MC_PRE_LEVEL_SELECT` callback.
* If transitioning back to the first floor, and `SameStage` is not set to `true`, Isaac's head will appear outside of the progress bar. Otherwise, Isaac's head will appear on the first floor.
* If repeating the last floor, and `SameStage` is not set to `true`, Isaac's head will move from the previous stage to the last one. Otherwise, Isaac's head will appear on the last floor.
???+ warning "Warning"
This function is useful if you want to move the player to the first stage, or want to repeat the last stage on the progress bar of the transition screen, and have it be less jarring.
Configure whether the stage transition will display Isaac's head moving from one stage to the other (`false`) or not (`true`).
