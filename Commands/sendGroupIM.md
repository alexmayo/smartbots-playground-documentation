# sendGroupIM

Sends a message to group chat.

```javascript
Bot.sendGroupIM(groupuuid, message);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `groupuuid` | yes | The UUID of the group. |
| `message` | yes | The text message to send (can contain international characters). |

# Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

# Comments

* This command does **not** return `FAIL` if your bot lacks the "Join Group Chat" ability. Make sure the bot has sufficient group permissions before using this command.
* Message delivery is guaranteed even if the bot is offline (the message will be sent when the bot comes online).