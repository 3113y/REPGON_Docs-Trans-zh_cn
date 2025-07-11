---
tags:
  - Class
---
# Class "ProceduralEffect"

???+ info
    你可以通过以下函数获取此类:

    * [ProceduralItem.GetEffect()](ProceduralItem.md#geteffect)

    ???+ example "Example Code"
        ```lua
        local pItemEffect = ProceduralItemManager.GetProceduralItem(0):GetEffect(0)
        ```

## Functions
### GetActionProperty () {: aria-label='Functions' }
#### table GetActionProperty ( ) {: .copyable aria-label='Functions' }
| toType | int | target type |
When `GetActionType` returns `SPAWN_ENTITY`, the returned table has the following fields.
| scale | float | |
When `GetActionType` returns `CONVERT_ENTITY`, the returned table has the following fields.
| fromVariant | int | |
When `GetActionType` returns `FART`, the returned table has the following fields.
| damage | float | |
When `GetActionType` returns `AREA_DAMAGE`, the returned table has the following fields.
| id | int | |
| fromType | int | |
|:--|:--|:--|
| variant | int | |
When `GetActionType` returns `ADD_TEMPRORY_EFFECT`, the returned table has the following fields.
Returns a table that describes the action argument.
When `GetActionType` returns `USE_ACTIVE_ITEM`, the returned table has the following fields.
|Field|Type|Comment|
| type | int | |
| radius | float | |
| toVariant | int | target variant |

### GetActionType () {: aria-label='Functions' }
#### [ProceduralEffectActionType](enums/ProceduralEffectActionType.md) GetActionType ( ) {: .copyable aria-label='Functions' }
Returns what to do after the effect is triggered.

### GetConditionProperty () {: aria-label='Functions' }
#### table GetConditionProperty ( ) {: .copyable aria-label='Functions' }
| type |  int |
| variant |  int |
Returns a table that describes the condition argument.
When `GetConditionType` returns `ENTITY_SPAWN`, the returned table has the following fields.
|:--|:--|
|Field|Type|

### GetConditionType () {: aria-label='Functions' }
#### [ProceduralEffectConditionType](enums/ProceduralEffectConditionType.md) GetConditionType ( ) {: .copyable aria-label='Functions' }
Returns the timing when the effect was triggered.

### GetTriggerChance () {: aria-label='Functions' }
#### float GetTriggerChance ( ) {: .copyable aria-label='Functions' }
Values range from `0` to `1`.
