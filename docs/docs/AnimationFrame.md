---
tags:
  - Class
---
# Class "AnimationFrame"

Cached data for a single frame of one layer of an animation from an ANM2 file. Shared by all Sprites using the same ANM2 and cannot be modified.

Note that interpolation and root animations have already been baked into these values.

Otherwise, these values correspond to the same ones viewable in the ANM2 editor, and have been named the same way.

Obtained via [AnimationLayer:GetFrame()](AnimationLayer.md#getframe).

## Functions

### GetColor () {: aria-label='Functions' }
#### [const Color](Color.md) GetColor ( ) {: .copyable aria-label='Functions' }

___
### GetCrop () {: aria-label='Functions' }
#### [const Vector](Vector.md) GetCrop ( ) {: .copyable aria-label='Functions' }

___
### GetEndFrame () {: aria-label='Functions' }
#### int GetEndFrame ( ) {: .copyable aria-label='Functions' }
也就是说，本动画帧（AnimationFrame）在此帧之后将不再显示。
请注意，“结束帧”是下一动画帧（AnimationFrame）的起始帧。### GetHeight () {: aria-label='Functions' }
#### float GetHeight ( ) {: .copyable aria-label='Functions' }

___
### GetPivot () {: aria-label='Functions' }
#### [const Vector](Vector.md) GetPivot ( ) {: .copyable aria-label='Functions' }

___
### GetPos () {: aria-label='Functions' }
#### [const Vector](Vector.md) GetPos ( ) {: .copyable aria-label='Functions' }

___
### GetRotation () {: aria-label='Functions' }
#### float GetRotation ( ) {: .copyable aria-label='Functions' }

___
### GetScale () {: aria-label='Functions' }
#### [const Vector](Vector.md) GetScale ( ) {: .copyable aria-label='Functions' }

___
### GetStartFrame () {: aria-label='Functions' }
#### int GetStartFrame ( ) {: .copyable aria-label='Functions' }

___
### GetWidth () {: aria-label='Functions' }
#### float GetWidth ( ) {: .copyable aria-label='Functions' }

___
### IsInterpolated () {: aria-label='Functions' }
#### boolean IsInterpolated ( ) {: .copyable aria-label='Functions' }

___
### IsVisible () {: aria-label='Functions' }
#### boolean IsVisible ( ) {: .copyable aria-label='Functions' }

___
