# Commands

Commands are being sent to the bot by calling the javascript method of `*Bot*`.

```javascript
Bot.im("Glaznah Gassner", "Hello there!");
```

| **Access Rights** |
|----|
| `[isMyOwner](./Commands/isMyOwner.md)` | Returns if the bot is owned by the avatar. |
| `[isMyManager](./Commands/isMyManager.md)` | Returns if the avatar is a Trusted Manager for the bot. |
| `[isOnline](./Commands/isOnline.md)` | Returns true/false if the bot is online. |
| **Avatar Info** |
| `[avatarInfo](./Commands/avatarInfo.md)` | Returns the Second Life avatar details. |
| `[checkScriptedAgent](./Commands/checkScriptedAgent.md)` | Returns if the resident is a scripted agent known by SmartBots. Includes all SmartBots bots and other residents our system considers bots or scripted agents. |
| **Status** |
| `[status](./Commands/status.md)` | Returns the online status of the bot. |
| `[statusExt](./Commands/statusExt.md)` | Returns the online status of the bot (with extended information). |
| `[login](./Commands/login.md)` | Initiates bot login sequence. |
| `[logout](./Commands/logout.md)` | Initiates bot logout sequence. |
| **Messaging** |
| `[say](https://s)` | Says message over a specific chat channel. |
| `[im](./Commands/im.md)` | Sends Instant Message to a specific avatar. |
| `[replyDialog](./Commands/replyDialog.md)` | Virtually "presses" a pop-up dialog button displayed by an in-world script. |
| `[startTyping](./Commands/startTyping.md)` | Sends "typing" in chat to a specific user. |
| `[stopTyping](./Commands/stopTyping.md)` | Stops sending "typing" in chat to a specific user. |
| **Friendship** |
| `[acceptFriendshipOffer](./Commands/acceptFriendshipOffer.md)` | Accept (or reject) a friendship offer sent by another avatar. |
| `[offerFriendship](https://o)` | Offers friendship to a resident. |
| **Group Control** |
| `[acceptGroupOffer](./Commands/acceptGroupOffer.md)` | Accept (or reject) a group invitation sent by another avatar. |
| `[activateGroup](./Commands/activateGroup.md)` | Activates a specific group (e.g., to get build rights on a parcel). |
| `[groupInfo](./Commands/groupInfo.md)` | Returns the Second Life group details. |
| `[joinGroup](./Commands/joinGroup.md)` | Tries to join a group by UUID. |
| `[leaveGroup](./Commands/leaveGroup.md)` | Commands bot to leave the group specified by a UUID. |
| `[listGroups](./Commands/listGroups.md)` | Returns a list of the Second Life groups the bot is a member of. |
| `[revokeGroupRole](./Commands/revokeGroupRole.md)` | Removes a group member from a specific role. |
| `[sendGroupIM](./Commands/sendGroupIM.md)` | Sends a message to group chat. |
| `[sendNotice](https://s)` | Sends a notice to the group. |
| `[setGroupRole](./Commands/setGroupRole.md)` | Puts a member of a group in a specific role. |
| **Group Members Control** |
| `[ejectGroupMember](./Commands/ejectGroupMember.md)` | Ejects residents from the group. |
| `[inviteGroup](./Commands/inviteGroup.md)` | Sends a group invitation to a specific resident. |
| **Inventory** |
| `[acceptInventoryOffer](./Commands/acceptInventoryOffer.md)` | Accept (or reject) an inventory offer sent by another avatar or in-world script. |
| `[listInventory](./Commands/listInventory.md)` | Returns an inventory list of the given folder. |
| `[giveInventory](./Commands/giveInventory.md)` | Commands bot to send an inventory item or folder to a specific avatar. |
| `[deleteInventory](./Commands/deleteInventory.md)` | Commands bot to delete an inventory item. |
| `[createNotecard](./Commands/createNotecard.md)` | Creates a notecard with the desired contents in the bot's inventory. |
| `[editNotecard](./Commands/editNotecard.md)` | Edits a notecard in the bot's inventory. |
| `[readNotecard](./Commands/readNotecard.md)` | Reads a notecard in the bot's inventory. |
| **Appearance** |
| `[takeoff](./Commands/takeoff.md)` | Removes a clothing item, body part, or attachment (opposite of the wear command). |
| `[wear](./Commands/wear.md)` | Commands bot to wear a clothing item, body part, or attach an object. |
| **Money** |
| `[getBalance](./Commands/getBalance.md)` | Retrieves the current bot's L$ balance. |
| `[giveMoney](./Commands/giveMoney.md)` | Commands bot to send money (L$) to a specific avatar. |
| **Movement** |
| `[fly](./Commands/fly.md)` | Starts or stops flying. |
| `[getLocation](./Commands/getLocation.md)` | Returns current location of the bot. |
| `[move](./Commands/move.md)` | Starts or stops bot movement and rotations. |
| `[sit](./Commands/sit.md)` | Commands bot to sit on a specific prim. Allows saving this object as a permanent location. |
| `[teleport](./Commands/teleport.md)` | Teleports bot to a specific location. |
| `[walkTo](https://w)` | Walks to a position within the current region. |
| `[turnTo](./Commands/turnTo.md)` | Turns bot towards specified heading. |
| **Other Avatars Interaction** |
| `[key2name](./Commands/key2name.md)` | Returns avatar Second Life name by UUID. |
| `[name2key](./Commands/name2key.md)` | Returns the UUID of a resident by name. |
| `[offerTeleport](./Commands/offerTeleport.md)` | Sends a teleport offer to a resident. |
| `[acceptTeleportOffer](./Commands/acceptTeleportOffer.md)` | Accept (or reject) a teleport offer sent by another avatar. |
| **World Interaction** |
| `[scanNearbyAvatars](./Commands/scanNearbyAvatars.md)` | Scans the current region for other avatars. |
| `[trackAvatars](./Commands/trackAvatars.md)` | Starts tracking avatars and reports their position in `[avatar_tracker_update](./Events/avatar_tracker_update.md)` event. |
| `[takeInworldPrim](./Commands/takeInworldPrim.md)` | Takes (de-rezzes) or copies an in-world prim into the bot's inventory. *Not available for QubicBot yet?* |
| `[touchAttachment](./Commands/touchAttachment.md)` | Touches an attachment of the bot (HUD or wearable object). |
| `[touchPrim](./Commands/touchPrim.md)` | Touches an in-world object (prim) by its UUID. |
| **Region (Sim) Control** |
| `[regionRestart](./Commands/regionRestart.md)` | Requests to restart the current region of the bot. |
| `[regionRestartCancel](./Commands/regionRestartCancel.md)` | Cancels a pending restart of the current region. |