# readNotecard

Reads a notecard from the bot's inventory.

```javascript
Bot.readNotecard("b572d860-c5cf-e023-a6b2-408f30266acc");
```

## Input

| Variable | Required | Description |
|----|----|----|
| `uuid` | yes | The inventory UUID of the notecard. Use the Personal Bot Control Panel to get this UUID. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |
| `text` | string | The contents of the notecard. |