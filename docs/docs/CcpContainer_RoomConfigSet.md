---
tags:
  - Class
search:
  boost: 0.25
---
# Class "RoomConfigSet"

???+ info
    你可以通过以下函数获取此类:

    * [RoomConfigStage.GetRoomSet()](RoomConfigStage.md#getroomset)

    ???+ example "Example Code"
        ```lua
        local roomConfigSet = RoomConfig.GetStage(StbType.BASEMENT):GetRoomSet(0)`
        ```
## Operators
### __len () {: aria-label='Operators' }
[ ](#){: .abrep .tooltip .badge }
长度 (#) 操作。返回列表中实体的数量

## Functions
### Get () {: aria-label='Functions' }
[ ](#){: .abrep .tooltip .badge }
返回列表中指定索引处的 [RoomConfigRoom](https://wofsauge.github.io/IsaacDocs/rep/RoomConfig_Room.html)。
### Size {: aria-label='Variables' }
[ ](#){: .const .tooltip .badge } [ ](#){: .abrep .tooltip .badge }
#### const int Size  {: .copyable aria-label='Variables' }

列表中的实体数量.

___