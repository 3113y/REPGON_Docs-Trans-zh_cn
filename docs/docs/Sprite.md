---
tags:
  - Class
---
# Class "Sprite"

## Modified Constructors

### Sprite () {: aria-label='Modified Constructors' }
#### [Sprite](Sprite.md),bool Sprite ( string ANM2Path, bool LoadGraphics = true ) {: .copyable aria-label='Modified Constructors' }
Added two optional arguments, the function now returns two values: [Sprite](Sprite.md) object and the bool signifying whether the sprite was loaded successfully or not.

### ReplaceSpritesheet () {: aria-label='Modified Functions' }
#### void ReplaceSpritesheet ( int LayerId, string PngFilename, boolean LoadGraphics = false ) {: .copyable aria-label='Modified Functions' }
Now accepts an optional `bool` to determine if Sprite:LoadGraphics should be called after replacing the spritesheet. In most cases, you'll want to do this.

### SetOverlayFrame () {: aria-label='Modified Functions' }
#### void SetOverlayFrame ( int FrameNum ) {: .copyable aria-label='Modified Functions' }
New overload for `SetOverlayFrame()` that sets the frame for the current animation without stopping it, akin to the one for `SetFrame()`.

### Stop () {: aria-label='Modified Functions' }
#### void Stop ( boolean StopOverlay = true ) {: .copyable aria-label='Modified Functions' }
Now accepts an optional `bool` for whether to also stop the overlay animation. Defaults to true.

### ClearCustomChampionShader () {: aria-label='Functions' }
#### void ClearCustomChampionShader ( ) {: .copyable aria-label='Functions' }
Removes any custom `coloroffset_champion` shader applied by `sprite:SetCustomChampionShader(path)`.

### ClearCustomShader () {: aria-label='Functions' }
#### void ClearCustomShader ( ) {: .copyable aria-label='Functions' }
Removes any custom `coloroffset` shader applied by `sprite:SetCustomShader(path)`.

### Continue () {: aria-label='Functions' }
#### void Continue ( boolean ContinueOverlay = true ) {: .copyable aria-label='Functions' }
If the animation is currently stopped, makes it start playing again from the current frame. Will not restart a finished, non-looping animation.

### ContinueOverlay () {: aria-label='Functions' }
#### void ContinueOverlay ( ) {: .copyable aria-label='Functions' }
Same as above, but only for the overlay animation.

### GetAllAnimationData () {: aria-label='Functions' }
#### [AnimationData](AnimationData.md)[] GetAllAnimationData ( ) {: .copyable aria-label='Functions' }
Returns a table of [AnimationData](AnimationData.md) representing all animations in this anm2 file.

### GetAllLayers () {: aria-label='Functions' }
#### [LayerStates](LayerState.md)[] GetAllLayers ( ) {: .copyable aria-label='Functions' }
Returns a table of all [LayerStates](LayerState.md) in this Sprite.

### GetAnimationData () {: aria-label='Functions' }
#### [AnimationData](AnimationData.md) GetAnimationData ( string AnimationName ) {: .copyable aria-label='Functions' }

___
### GetCurrentAnimationData () {: aria-label='Functions' }
#### [AnimationData](AnimationData.md) GetCurrentAnimationData ( ) {: .copyable aria-label='Functions' }

___
### GetLayer () {: aria-label='Functions' }
#### [LayerState](LayerState.md) GetLayer ( int LayerId ) {: .copyable aria-label='Functions' }
Returns the layer data from the provided layer id.

### GetLayerFrameData () {: aria-label='Functions' }
#### [AnimationFrame](AnimationFrame.md) GetLayerFrameData ( int Layer ) {: .copyable aria-label='Functions' }
Returns the [AnimationFrame](AnimationFrame.md) currently being displayed on the specified layer.

### GetNullFrame () {: aria-label='Functions' }
#### [NullFrame](NullFrame.md) GetNullFrame ( string LayerName ) {: .copyable aria-label='Functions' }
Returns the [NullFrame](NullFrame.md) from the provided layer name.

### GetOverlayAnimationData () {: aria-label='Functions' }
#### [AnimationData](AnimationData.md) GetOverlayAnimationData ( ) {: .copyable aria-label='Functions' }
Returns the [AnimationData](AnimationData.md) of the currently playing overlay.

### GetOverlayLayerFrameData () {: aria-label='Functions' }
#### [AnimationFrame](AnimationFrame.md) GetOverlayLayerFrameData ( int Layer ) {: .copyable aria-label='Functions' }
Returns the [AnimationFrame](AnimationFrame.md) currently being displayed on the specified layer of the overlay animation.

### GetOverlayNullFrame () {: aria-label='Functions' }
#### [NullFrame](NullFrame.md) GetOverlayNullFrame ( string LayerName ) {: .copyable aria-label='Functions' }
Returns the [NullFrame](NullFrame.md) from the provided layer name of the overlay animation.

### GetRenderFlags () {: aria-label='Functions' }
#### [AnimRenderFlags](enums/AnimRenderFlags.md) GetRenderFlags ( ) {: .copyable aria-label='Functions' }

___
### HasCustomChampionShader () {: aria-label='Functions' }
#### boolean HasCustomChampionShader ( string ShaderPath ) {: .copyable aria-label='Functions' }
Returns true if the specified custom champion shader is currently loaded (see `SetCustomChampionShader` below). If no string is provided, returns true if ANY custom champion shader is applied.

### HasCustomShader () {: aria-label='Functions' }
#### boolean HasCustomShader ( string ShaderPath ) {: .copyable aria-label='Functions' }
Returns true if the specified custom shader is currently loaded (see `SetCustomShader` below). If no string is provided, returns true if ANY custom shader is applied.

### IsOverlayEventTriggered () {: aria-label='Functions' }
#### boolean IsOverlayEventTriggered ( string EventName ) {: .copyable aria-label='Functions' }
Returns `true` if the currently playing overlay animation just reached the event with the provided name.

### SetCustomChampionShader () {: aria-label='Functions' }
#### void SetCustomChampionShader ( string ShaderPath ) {: .copyable aria-label='Functions' }
The custom champion shader will only be used by the game if the entity is actually a champion.
You can also set a per-layer shader via [LayerState](LayerState.md).
Specify a custom champion shader file for this Sprite to use instead of the usual `coloroffset_champion` shader. Provided path is expected to start at `.../resources/` and to find both a .vs and .fs file at that location. For example: `sprite:SetCustomChampionShader("shaders/my_shader")` will load `.../resources/shaders/my_shader.vs` and `.../resources/shaders/my_shader.fs`.
Note that the custom shader must take the exact same inputs as the default `coloroffset_champion` shader the game uses (it has one additional input compared to `coloroffset`).

### SetCustomShader () {: aria-label='Functions' }
#### void SetCustomShader ( string ShaderPath ) {: .copyable aria-label='Functions' }
Note that the custom shader must take the exact same inputs as the default `coloroffset` shader the game uses. The gold and dogma shaders also use the same inputs, and can be a good reference.
This custom shader will not be used by the game if the entity is a champion, or if it has the gold/dogma shader applied.
You can also set a per-layer shader via [LayerState](LayerState.md).
Specify a custom shader file for this Sprite to use instead of the default `coloroffset` shader. Provided path is expected to start at `.../resources/` and to find both a .vs and .fs file at that location. For example: `sprite:SetCustomShader("shaders/my_shader")` will load `.../resources/shaders/my_shader.vs` and `.../resources/shaders/my_shader.fs`.
### SetOverlayLayerFrame () {: aria-label='Functions' }
#### void SetOverlayLayerFrame ( int Layer, int Frame ) {: .copyable aria-label='Functions' }

___
### SetRenderFlags () {: aria-label='Functions' }
#### void SetRenderFlags ( [AnimRenderFlags](enums/AnimRenderFlags.md) Flags ) {: .copyable aria-label='Functions' }

___
### StopOverlay () {: aria-label='Functions' }
#### void StopOverlay ( ) {: .copyable aria-label='Functions' }

___
### WasOverlayEventTriggered () {: aria-label='Functions' }
#### boolean WasOverlayEventTriggered ( string EventName ) {: .copyable aria-label='Functions' }

___
