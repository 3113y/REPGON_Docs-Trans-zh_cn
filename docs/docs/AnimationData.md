---
tags:
  - Class
---
# Class "AnimationData"

Cached data for one animation from a loaded ANM2 file. Shared by all Sprites using the same ANM2 and cannot be modified.

Can be obtained via [Sprite:GetAnimationData()](Sprite.md#getanimationdata), [Sprite:GetCurrentAnimationData()](Sprite.md#getanimationdata) or [Sprite:GetOverlayAnimationData()](Sprite.md#getanimationdata).

## Functions

### GetAllLayers () {: aria-label='Functions' }
#### [AnimationLayer](AnimationLayer.md)[] GetAllLayers ( ) {: .copyable aria-label='Functions' }
返回一个动画层（AnimationLayers）表，按从下到上的顺序排列（**不**按层ID排序）。

### GetLayer () {: aria-label='Functions' }
#### [AnimationLayer](AnimationLayer.md) GetLayer ( int LayerId ) {: .copyable aria-label='Functions' }
通过动画层的ID号获取一个动画层。

### GetLength () {: aria-label='Functions' }
#### int GetLength ( ) {: .copyable aria-label='Functions' }
此动画的帧数长度。### GetName () {: aria-label='Functions' }
#### string GetName ( ) {: .copyable aria-label='Functions' }

___
### IsLoopingAnimation () {: aria-label='Functions' }
#### boolean IsLoopingAnimation ( ) {: .copyable aria-label='Functions' }

___

