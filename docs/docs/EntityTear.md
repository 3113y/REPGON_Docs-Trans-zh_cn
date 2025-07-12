---
tags:
  - Class
---
# Class "EntityTear"

## Class Diagram
--8<-- "docs/snippets/EntityClassDiagram_NewFunkyMode.md"
## Modified Functions

### ResetSpriteScale () {: aria-label='Modified Functions' }
#### void ResetSpriteScale ( boolean Force = false ) {: .copyable aria-label='Modified Functions' }
现在接受一个 `Force` 参数，用于强制眼泪重新评估应该播放哪种眼泪缩放动画。

### GetDeadEyeIntensity () {: aria-label='Functions' }
#### float GetDeadEyeIntensity ( ) {: .copyable aria-label='Functions' }
返回眼泪因“死亡之眼”道具产生的强度值，该值介于 `0` 和 `1` 之间。

### GetDeadEyeSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetDeadEyeSprite ( ) {: .copyable aria-label='Functions' }
返回“死亡之眼”道具使用的红色光环精灵图。

### GetTearEffectSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetTearEffectSprite ( ) {: .copyable aria-label='Functions' }
返回像“火之思维”和“神秘液体”等眼泪变体所使用的眼泪特效精灵图。

### GetTearHaloSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetTearHaloSprite ( ) {: .copyable aria-label='Functions' }
返回“神格”眼泪所使用的眼泪光晕精灵图。

### IsMultidimensionalTouched () {: aria-label='Functions' }
#### boolean IsMultidimensionalTouched ( ) {: .copyable aria-label='Functions' }
返回该眼泪是否是通过“多维宝宝”效果创建的。

### IsPrismTouched () {: aria-label='Functions' }
#### boolean IsPrismTouched ( ) {: .copyable aria-label='Functions' }
返回该眼泪是否是通过“天使棱镜”效果创建的。

### MakeMultidimensionalCopy () {: aria-label='Functions' }
#### [EntityTear](EntityTear.md) MakeMultidimensionalCopy ( ) {: .copyable aria-label='Functions' }
复制该眼泪并为其应用黑白效果，此效果与“多维宝宝”跟班所使用的效果相同。

### SetMultidimensionalTouched () {: aria-label='Functions' }
#### void SetMultidimensionalTouched ( boolean IsTouched ) {: .copyable aria-label='Functions' }
设置该眼泪是否是通过“天使棱镜”效果创建的。

### SetPrismTouched () {: aria-label='Functions' }
#### void SetPrismTouched ( boolean IsTouched ) {: .copyable aria-label='Functions' }
设置该眼泪是否是通过“天使棱镜”效果创建的。