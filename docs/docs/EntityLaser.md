---
tags:
  - Class
---
# Class "EntityLaser"

## Class Diagram
--8<-- "docs/snippets/EntityClassDiagram_NewFunkyMode.md"
## Modified Variables
___
### HomingType {: aria-label='Modified Variables' }
#### int HomingType  {: .copyable aria-label='Modified Variables' }
与默认值相同，但现在返回的是正确的整数值，而非用户数据.

___

## Functions

### GetDamageMultiplier () {: aria-label='Functions' }
#### float GetDamageMultiplier ( ) {: .copyable aria-label='Functions' }

___
### GetDisableFollowParent () {: aria-label='Functions' }
#### boolean GetDisableFollowParent ( ) {: .copyable aria-label='Functions' }

___
### GetHitList () {: aria-label='Functions' }
#### int GetHitList ( ) {: .copyable aria-label='Functions' }

___
### GetOneHit () {: aria-label='Functions' }
#### boolean GetOneHit ( ) {: .copyable aria-label='Functions' }

___
### GetScale () {: aria-label='Functions' }
#### float GetScale ( ) {: .copyable aria-label='Functions' }

___
### GetShrink () {: aria-label='Functions' }
#### boolean GetShrink ( ) {: .copyable aria-label='Functions' }

___
### GetTimeout () {: aria-label='Functions' }
#### int GetTimeout ( ) {: .copyable aria-label='Functions' }

___
### IsMultidimensionalTouched () {: aria-label='Functions' }
#### boolean IsMultidimensionalTouched ( ) {: .copyable aria-label='Functions' }
返回该激光是否是通过“多维宝宝”效果创建的。

___
### IsPrismTouched () {: aria-label='Functions' }
#### boolean IsPrismTouched ( ) {: .copyable aria-label='Functions' }
返回该激光是否是通过“天使棱镜”效果创建的。

___
### RecalculateSamplesNextUpdate () {: aria-label='Functions' }
#### void RecalculateSamplesNextUpdate ( ) {: .copyable aria-label='Functions' }
请求在下一次更新时完全重新计算激光的形状。可用于强制激光立即改变其最大距离/半径，而不是逐渐过渡到新值。对单次命中或非采样激光无效。

___
### ResetSpriteScale () {: aria-label='Functions' }
#### void ResetSpriteScale ( ) {: .copyable aria-label='Functions' }

___
### RotateToAngle () {: aria-label='Functions' }
#### void RotateToAngle ( float Angle, float Speed = 8.0 ) {: .copyable aria-label='Functions' }

___
### SetDamageMultiplier () {: aria-label='Functions' }
#### void SetDamageMultiplier ( float DamageMult ) {: .copyable aria-label='Functions' }

___
### SetDisableFollowParent () {: aria-label='Functions' }
#### void SetDisableFollowParent ( boolean Value ) {: .copyable aria-label='Functions' }

___
### SetPrismTouched () {: aria-label='Functions' }
#### void SetPrismTouched ( boolean IsTouched ) {: .copyable aria-label='Functions' }
设置该激光是否是通过“天使棱镜”效果创建的。

___
### SetScale () {: aria-label='Functions' }
#### void SetScale ( float Value ) {: .copyable aria-label='Functions' }

___
### SetShrink () {: aria-label='Functions' }
#### void SetShrink ( boolean Value ) {: .copyable aria-label='Functions' }

___
### SetTimeout () {: aria-label='Functions' }
#### void SetTimeout ( int Value ) {: .copyable aria-label='Functions' }

___