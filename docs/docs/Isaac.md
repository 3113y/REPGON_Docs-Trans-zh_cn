---
tags:
  - Global
  - Class
---
# Global Class "Isaac"
## Modified Functions

### FindByType () {: aria-label='Modified Functions' }
#### [Entity](Entity.md)[] FindByType ( [EntityType](https://wofsauge.github.io/IsaacDocs/rep/enums/EntityType.html) Type, int Variant = -1, int SubType = -1, boolean Cache = false, boolean IgnoreFriendly = false ) {: .copyable aria-label='Modified Functions' }
Same as vanilla, but much faster.

### FindInRadius () {: aria-label='Modified Functions' }
#### [Entity](Entity.md)[] FindInRadius ( [Vector](Vector.md) Position, float Radius, [EntityPartition](https://wofsauge.github.io/IsaacDocs/rep/enums/EntityPartition.html) Partitions = 0xFFFFFFFF  ) {: .copyable aria-label='Modified Functions' }
Same as in vanilla, but much faster and with fixed search for effects.

### GetRoomEntities () {: aria-label='Modified Functions' }
#### [Entity](Entity.md)[] GetRoomEntities ( ) {: .copyable aria-label='Modified Functions' }
Same as vanilla, but much faster.

### AllMarksFilled () {: aria-label='Functions' }
#### int AllMarksFilled ( [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) Character) {: .copyable aria-label='Functions' }
Checks if a given character has completed all marks and returns an integer representing the highest difficulty it was accomplished in.
- `0` - None
- `2` - Hard
The difficulties are as follows:
???- info "Note"
- `1` - Normal

### AllTaintedCompletion () {: aria-label='Functions' }
#### int AllTaintedCompletion ( [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) Character, [TaintedMarksGroup](enums/TaintedMarksGroup.md) Group) {: .copyable aria-label='Functions' }
- `0` - None
- `2` - Hard
The difficulties are as follows:
???- info "Note"
Checks if a given character has completed all the tainted unlock-related marks and returns an integer representing the highest difficulty it was accomplished in.
- `1` - Normal

### CanStartTrueCoop () {: aria-label='Functions' }
#### boolean CanStartTrueCoop ( ) {: .copyable aria-label='Functions' }

___
### CenterCursor () {: aria-label='Functions' }
#### void CenterCursor ( ) {: .copyable aria-label='Functions' }
Take in mind the screen center is NOT the center of the room necessarily, it's just the center of the game's window(center of the actual screen if you are on fullscreen).
Moves the windows mouse cursor to the center of the game's window. This is incredibly niche but useful if you want to use cursor controls for anything fancy and have full control over it. It wont move the cursor if Isaac.exe becomes out of focus.
???- info "Note"

### ClearBossHazards () {: aria-label='Functions' }
#### void ClearBossHazards ( boolean IgnoreNPCs = false ) {: .copyable aria-label='Functions' }
Kills all projectiles. Kills all non-friendly NPCs capable of keeping doors closed as well if `IgnoreNPCs` is false.

### ClearChallenge () {: aria-label='Functions' }
#### void ClearChallenge ( int challengeid) {: .copyable aria-label='Functions' }
Sets the challenge of the corresponding `challengeid` to completed.

### ClearCompletionMarks () {: aria-label='Functions' }
#### void ClearCompletionMarks ( [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) Character) {: .copyable aria-label='Functions' }
Deletes all completion marks for a given character.

### CreateTimer () {: aria-label='Functions' }
#### [EntityEffect](https://wofsauge.github.io/IsaacDocs/rep/EntityEffect.html) CreateTimer ( function Function, int Interval, int Times, boolean Persistent ) {: .copyable aria-label='Functions' }
This timer is called every game update. This means the timer only takes into consideration frames in which the game is actively running, not paused, and uses update frames for its Delay parameter (30 frames per second).
Spawns a timer EntityEffect. This entity will starting running `Function` function after `Interval` frames, and will repeat it `Times` amount of times. `Persistent` controls whether or not this timer "dies" in the current room, or persists across rooms.
???- info "Timer behavior"
If your use case requires that a timer takes paused time into account, stick with a custom timer running on a RENDER callback.

### CreateWeapon () {: aria-label='Functions' }
#### [Weapon](Weapon.md) CreateWeapon ( [WeaponType](https://wofsauge.github.io/IsaacDocs/rep/enums/WeaponType.html) Type, [Entity](Entity.md) Owner ) {: .copyable aria-label='Functions' }
Creates and returns a [Weapon](Weapon.md) object. It is not automatically useable by `owner` and `Isaac.SetWeaponType` must be used in tandem.

### DestroyWeapon () {: aria-label='Functions' }
#### void DestroyWeapon ( [Weapon](Weapon.md) Weapon ) {: .copyable aria-label='Functions' }
Destroys the provided [Weapon](Weapon.md) object.

### DrawLine () {: aria-label='Functions' }
#### void DrawLine ( [Vector](Vector.md) StartPos, [Vector](Vector.md) EndPos, [KColor](https://wofsauge.github.io/IsaacDocs/rep/KColor) StartColor, [KColor](https://wofsauge.github.io/IsaacDocs/rep/KColor) EndColor, int Thickness ) {: .copyable aria-label='Functions' }
Draws a line between the two given positions this render frame.

### DrawQuad () {: aria-label='Functions' }
#### void DrawQuad ( [Vector](Vector.md) TopLeftPos, [Vector](Vector.md) TopRightPos, [Vector](Vector.md) BottomLeftPos, [Vector](Vector.md) BottomRightPos, [KColor](https://wofsauge.github.io/IsaacDocs/rep/KColor) Color, int Thickness ) {: .copyable aria-label='Functions' }
Draws a line between the two given positions this render frame. Internally the game uses its own struct for this, DestinationQuad, but I haven't gotten to adding that to Lua yet :crocodile:

### FillCompletionMarks () {: aria-label='Functions' }
#### void FillCompletionMarks ( [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) Character) {: .copyable aria-label='Functions' }
Completes all completion marks for a given character.

### FindInCapsule () {: aria-label='Functions' }
#### [Entity](Entity.md)[] FindInCapsule ( [Capsule](Capsule.md) Capsule, [EntityPartitions](https://wofsauge.github.io/IsaacDocs/rep/enums/EntityPartition.html) Partitions = -1 ) {: .copyable aria-label='Functions' }
Return entities inside of given capsule, filtered by partitions mask.

### FindTargetPit () {: aria-label='Functions' }
#### int FindTargetPit ( [Vector](Vector.md) Position, [Vector](Vector.md) TargetPosition, int PitIndex = -1 ) {: .copyable aria-label='Functions' }

___
### GetAchievementIdByName () {: aria-label='Functions' }
#### int GetAchievementIdByName ( string Name ) {: .copyable aria-label='Functions' }
Gets the Achievement ID By Name.

### GetAxisAlignedUnitVectorFromDir () {: aria-label='Functions' }
#### [Vector](Vector.md) GetAxisAlignedUnitVectorFromDir ( [Direction](https://wofsauge.github.io/IsaacDocs/rep/enums/Direction.html) Direction = -1 ) {: .copyable aria-label='Functions' }

___
### GetBackdropIdByName () {: aria-label='Functions' }
#### int GetBackdropIdByName ( string BackdropName ) {: .copyable aria-label='Functions' }

___
### GetBossColorIdxByName () {: aria-label='Functions' }
#### int GetBossColorIdxByName ( string Name ) {: .copyable aria-label='Functions' }
Gets the boss color idx By Name, the idx is usually the subtype the boss needs to become the desired color. Granted, you actually need to give your color entry a name on the xml for this to work (suffix wont work usually, since its not mandatory).

### GetClipboard () {: aria-label='Functions' }
#### string GetClipboard ( ) {: .copyable aria-label='Functions' }
Gets the contents of the clipboard as long as they are in text form, otherwise it will just return nil.

### GetCollectibleSpawnPosition () {: aria-label='Functions' }
#### [Vector](Vector.md) GetCollectibleSpawnPosition ( [Vector](Vector.md) Position ) {: .copyable aria-label='Functions' }

___
### GetCompletionMark () {: aria-label='Functions' }
#### int GetCompletionMark ( [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) Character, [CompletionType](enums/CompletionType.md) Mark) {: .copyable aria-label='Functions' }
Gets a completion mark value for a specific character, value from `0` to `2` (0 = not accomplished, 1 = normal, 2 = hard).

### GetCompletionMarks () {: aria-label='Functions' }
#### table GetCompletionMarks ( [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) Character) {: .copyable aria-label='Functions' }
if (Isaac.GetCompletionMarks(0).Delirium > 0) then --doing it the lazy way, fitting deliriums theme
* Satan: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
if (marks.MomsHeart > 0) then
print("got mom")
```lua
Returns a table containing all the marks for the character.
```
???- info "Table structure & usage"
* Delirium: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* MegaSatan: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* Mother: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* UltraGreed: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* BlueBaby: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
end
if (marks.Lamb >= 2) then
local marks = Isaac.GetCompletionMarks(0)
* UltraGreedier: Mostly redundant with UltraGreed when it has a value of 2, no need to set it
print("GOATED ON H4RD")
* BossRush: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
print("Got Deli")
* Beast: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* Isaac: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* PlayerType: containing the [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) associated to the marks
* Lamb: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* MomsHeart: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* Hush: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
- The table has the following fields:

### GetCurrentStageConfigId () {: aria-label='Functions' }
#### [StbType](enums/StbType.md) GetCurrentStageConfigId ( ) {: .copyable aria-label='Functions' }
Gets the current stageconfigId/stbType, or whatever you wanna call the id of the stages.xml, for the current stage.

### GetCursorSprite () {: aria-label='Functions' }
#### [Sprite](Sprite.md) GetCursorSprite ( ) {: .copyable aria-label='Functions' }
Returns the cursor sprite that is rendered when ``Options.MouseControl`` is set to true.

### GetCutsceneIdByName () {: aria-label='Functions' }
#### table GetCutsceneIdByName ( string Name ) {: .copyable aria-label='Functions' }
Gets the Cutscene ID By Name.

### GetDwmWindowAttribute () {: aria-label='Functions' }
#### [DwmWindowAttribute](enums/DwmWindowAttribute.md) GetDwmWindowAttribute ( ) {: .copyable aria-label='Functions' }

___
### GetEntitySubTypeByName () {: aria-label='Functions' }
#### int GetEntitySubTypeByName ( string Name ) {: .copyable aria-label='Functions' }
Gets the entity SubType by entity name.

### GetGiantBookIdByName () {: aria-label='Functions' }
#### int GetGiantBookIdByName ( string Name ) {: .copyable aria-label='Functions' }
Gets a GiantBook Id by name. For vanilla giantbooks, the png filename, from the gfx xml attribute, is used as the giantbook name.

### GetLoadedModules () {: aria-label='Functions' }
#### table GetLoadedModules ( ) {: .copyable aria-label='Functions' }
Returns a key - value table containing all loaded script files, where the key is the name or path of a given script file, and the value the return value of that file after loading. (In most cases its true or a table)

### GetLocalizedString () {: aria-label='Functions' }
#### string GetLocalizedString ( string Category, string Key, int Language ) {: .copyable aria-label='Functions' }
Returns the translation string associated with the given key in the given category. The translation is given in the language ID/language code given as parameter.

### GetModChallengeClearCount () {: aria-label='Functions' }
#### int GetModChallengeClearCount ( int challengeid ) {: .copyable aria-label='Functions' }
Returns the number of times a custom challenge was cleared. It resets if its ever set as not Done.

### GetNullItemIdByName () {: aria-label='Functions' }
#### int GetNullItemIdByName ( string NullItemName ) {: .copyable aria-label='Functions' }

___
### GetPersistentGameData () {: aria-label='Functions' }
#### [PersistentGameData](PersistentGameData.md) GetPersistentGameData ( ) {: .copyable aria-label='Functions' }

___
### GetPoolIdByName () {: aria-label='Functions' }
#### [ItemPoolType](https://wofsauge.github.io/IsaacDocs/rep/enums/ItemPoolType.html) GetPoolIdByName ( string PoolName ) {: .copyable aria-label='Functions' }
Returns the ID of a given custom pool. Returns `-1` if the pool is not found.

### GetRenderPosition () {: aria-label='Functions' }
#### [Vector](Vector.md) GetRenderPosition ( [Vector](Vector.md) Position, boolean Scale = true ) {: .copyable aria-label='Functions' }       

___
### GetString () {: aria-label='Functions' }
#### string GetString ( string Category, string Key ) {: .copyable aria-label='Functions' }
Returns the translation string associated with the given key in the given category. The translation is given in the currently selected language.

### GetWindowTitle () {: aria-label='Functions' }
#### string GetWindowTitle ( ) {: .copyable aria-label='Functions' }
Returns the appended text on the game's window title.

### IsChallengeDone () {: aria-label='Functions' }
#### boolean IsChallengeDone ( int challengeid ) {: .copyable aria-label='Functions' }
Returns `true` if the challenge of the corresponding challengeid is completed.

### IsInGame () {: aria-label='Functions' }
#### boolean IsInGame ( ) {: .copyable aria-label='Functions' }
Returns `true` if `Game` is non-nil and the current state is correct.

### LevelGeneratorEntry () {: aria-label='Functions' }
#### [LevelGeneratorEntry](LevelGeneratorEntry.md) LevelGeneratorEntry ( ) {: .copyable aria-label='Functions' }
Creates a new blank [LevelGeneratorEntry](LevelGeneratorEntry.md) object.

### MarkChallengeAsNotDone () {: aria-label='Functions' }
#### void MarkChallengeAsNotDone ( int challengeid ) {: .copyable aria-label='Functions' }
Sets the challenge as not done.

### PlayCutscene () {: aria-label='Functions' }
#### int PlayCutscene ( int ID, boolean ClearGameState = false ) {: .copyable aria-label='Functions' }
Plays the Cutscene of the provided ID. Use Isaac.GetCutsceneIdByName to get the IDs, or the enum for the vanilla ones if you prefer.

### SetClipboard () {: aria-label='Functions' }
#### boolean SetClipboard ( string ClipboardData ) {: .copyable aria-label='Functions' }
Sets the contents of the clipboard to the provided string.

### SetCompletionMark () {: aria-label='Functions' }
#### void SetCompletionMark ( [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) Character, [CompletionType](enums/CompletionType.md) Mark, int Value) {: .copyable aria-label='Functions' }
Sets a completion mark of a character to match a specific value from `0` to `2` (0 = not accomplished, 1 = normal, 2 = hard).

### SetCompletionMarks () {: aria-label='Functions' }
#### void SetCompletionMarks ( table Marks ) {: .copyable aria-label='Functions' }
* Satan: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
```lua
Isaac.SetCompletionMarks(marks) --Impacts the changes on the player
```
???- info "Table structure & usage"
* Delirium: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* MegaSatan: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* PlayerType: containing the [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) asociated to the marks
Sets the completion marks of a character to match an input table. Requires a table containing all the marks for the character, getting it from [GetCompletionMarks](Isaac.md#getcompletionmarks) is advised for convenience.
* Mother: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* UltraGreed: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* BlueBaby: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* UltraGreedier: Mostly redundant with UltraGreed when it has a value of 2, no need to set it
* BossRush: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
marks.BlueBaby = 0 --Removes the BlueBaby Mark if its present
* Beast: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* Isaac: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* Lamb: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
* MomsHeart: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
local marks = Isaac.GetCompletionMarks(0) --getting the current table
- The table needs the following fields:
marks.Satan = 1 --Isaac will now have the normal mark on Satan
* Hush: value of [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) 0-2 indicating the completion
marks.MomsHeart = 2 --Isaac now will have the hard mark on MHeart

### SetCurrentFloorBackdrop () {: aria-label='Functions' }
#### void SetCurrentFloorBackdrop ( int BackdropId ) {: .copyable aria-label='Functions' }
Changes the default room backdrop for the current floor to match the input id. This change wont persists on save/continue so make sure to account for that.

### SetCurrentFloorMusic () {: aria-label='Functions' }
#### void SetCurrentFloorMusic ( int MusicId ) {: .copyable aria-label='Functions' }
Changes the music track for the current floor to match the input id. This change wont persists on save/continue so make sure to account for that.

### SetCurrentFloorName () {: aria-label='Functions' }
#### void SetCurrentFloorName ( string Name ) {: .copyable aria-label='Functions' }
Changes the display name for the current floor to match the input id. This change wont persists on save/continue so make sure to account for that.

### SetDwmWindowAttribute () {: aria-label='Functions' }
#### void SetDwmWindowAttribute ( [DwmWindowAttribute](enums/DwmWindowAttribute.md) Attribute ) {: .copyable aria-label='Functions' }

___
### SetIcon () {: aria-label='Functions' }
#### void SetIcon ( int IsaacIcon OR string IconPath, boolean BypassSize) {: .copyable aria-label='Functions' }
`IconPath` accepts a path to a .ico file.
Sets the 16x16 icon located on the game window. Does not update the icon elsewhere, such as the task bar.
`IsaacIcon` is `0` for the normal icon, `1` for the Tainted icon.
`BypassSize` bypasses the 16x16 resolution cap.

### SetWindowTitle () {: aria-label='Functions' }
#### void SetWindowTitle ( string Title ) {: .copyable aria-label='Functions' }
Sets the appended text on the game's window title.

### ShowErrorDialog () {: aria-label='Functions' }
#### [DialogReturn](enums/DialogReturn.md) ShowErrorDialog ( string Title, string Text, [DialogIcons](enums/DialogIcons.md) Icon = DialogIcons.ERROR, [DialogButtons](enums/DialogButtons.md) Buttons = DialogButtons.OK ) {: .copyable aria-label='Functions' }
Take in mind that gamepad wont work for this popup, you'll need to use mouse/keyboard or touchscreen, and the window title wont show up on some enviroments like the steam deck, so dont rely on it too much.
Displays a Win32 message box. Can be controlled with the `icon` and `buttons` parameters. Returns a [`DialogReturn`](enums/DialogReturn.md) value that indicates the button pressed.
???- info "Note"

### StartNewGame () {: aria-label='Functions' }
#### void StartNewGame ( [PlayerType](https://wofsauge.github.io/IsaacDocs/rep/enums/PlayerType.html) Character, [Challenge](https://wofsauge.github.io/IsaacDocs/rep/enums/Challenge.html) Challenge = ChallengeType.CHALLENGE_NULL, [Difficulty](https://wofsauge.github.io/IsaacDocs/rep/enums/Difficulty.html) Mode = Difficulty.DIFFICULTY_NORMAL, int Seed = Random ) {: .copyable aria-label='Functions' }
Starts a new game using the specified arguments. Can be used from the main menu.

### TriggerWindowResize () {: aria-label='Functions' }
#### void TriggerWindowResize ( ) {: .copyable aria-label='Functions' }
Simulates a window resize, useful to refresh some option changes like `MaxRenderScale`.

### WorldToMenuPosition () {: aria-label='Functions' }
#### [Vector](Vector.md) WorldToMenuPosition ( [MainMenu](enums/MainMenuType.md) MenuId, [Vector](Vector.md) Position ) {: .copyable aria-label='Functions' }
Converts the World position from input to a pinned main menu position that varies depending on the enum selected. It's important to reconvert this every frame, in a similar fashion to WorldToRender, in order to properly render when menus are changed or the window is resized.
