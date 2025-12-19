# takeoff

Removes a clothing item, body part, or attachment (the opposite of the `[wear](./wear.md)` command).

```javascript
Bot.takeoff(uuid);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `uuid` | yes | The inventory UUID of the item. Use the Personal Bot Control Panel to get this UUID. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |