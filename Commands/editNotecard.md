# editNotecard

Edits a notecard in the bot's inventory.

```javascript
Bot.editNotecard(
  "b572d860-c5cf-e023-a6b2-408f30266acc",
  "Hello! This is the new contents of the notecard!"
);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `uuid` | yes | The inventory UUID of the item. Use the Personal Bot Control Panel to get this UUID. |
| `text` | yes | The updated contents of the notecard. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| **success** | bool | true if command completed successfully |
| **error** | string | error string if command has failed |