# leaveGroup

Commands the bot to leave the group specified by a UUID.

```javascript
Bot.leaveGroup(groupuuid);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `groupuuid` | yes | The UUID of the group |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |