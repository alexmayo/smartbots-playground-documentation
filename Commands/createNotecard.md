# createNotecard

Creates a notecard with the desired contents in the bot's inventory.

```javascript
Bot.createNotecard(
  "",
  "My new notecard",
  "This is a test notecard description",
  "Hello!\nThis is a new line but also the contents of my new notecard!"
);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `folder` |    | UUID of an inventory folder where the notecard will be created. If left blank, the notecard will be created in the **Notecards** folder within your bot's inventory. |
| `name` | yes | Name of the notecard |
| `description` |    | Optional description for the notecard |
| `text` | yes | The contents of the notecard |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | true if command completed successfully |
| `error` | string | error string if command has failed |
| `uuid` | string | UUID of the notecard within your bot's inventory |