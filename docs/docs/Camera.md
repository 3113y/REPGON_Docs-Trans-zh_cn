---
tags:
  - Class
---
# Class "Camera"

???+ info
    You can get this class by using the following functions:

    * [Room:GetCamera()](Room.md#getcamera)

    ???+ example "Example Code"
        ```lua
        local camera = Game():GetRoom():GetCamera()
        ```
        
## Functions

### IsPosVisible () {: aria-label='Functions' }
#### boolean IsPosVisible ( [Vector](Vector.md) Pos ) {: .copyable aria-label='Functions' }
返回世界中的某个位置是否在相机的可见范围内。

### SetFocusPosition () {: aria-label='Functions' }
#### void SetFocusPosition ( [Vector](Vector.md) Pos ) {: .copyable aria-label='Functions' }
仅当当前房间大小大于 1x1 时，相机才会移动。如果房间大小为 1x1 或更小，相机将保持静止，此函数将不起作用。
此函数必须在诸如 `ModCallbacks.MC_POST_UPDATE` 之类的更新回调中调用，否则游戏将覆盖相机的位置。
设置相机当前的聚焦位置，使其向指定位置移动。

### SnapToPosition () {: aria-label='Functions' }
#### void SnapToPosition ( [Vector](Vector.md) Pos ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
立即将相机的位置设置为指定位置。
此函数似乎仅在“主动相机”关闭时有效。
仅当当前房间大小大于 1x1 时，相机才会移动。如果房间大小为 1x1 或更小，相机将保持静止，此函数将不起作用。
此函数必须在诸如 `ModCallbacks.MC_POST_RENDER` 之类的渲染回调中调用，否则游戏将覆盖相机的位置。