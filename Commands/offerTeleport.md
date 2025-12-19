# offerTeleport

Sends a teleport offer to a resident.

```javascript
Bot.offerTeleport(avatar, message);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `avatar` | yes | The UUID of the resident. |
| `message` | optional | Optional message to send along with the teleport offer. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |