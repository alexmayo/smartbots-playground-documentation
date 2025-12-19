# giveInventory

Commands the bot to send an inventory item or folder to a specific avatar.

```javascript
Bot.giveInventory(avatar, object);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `avatar` | yes | The avatar UUID |
| `object` | yes | The inventory item or folder UUID. Use the Personal Bot Control Panel to get this UUID. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Error messages

Bot checks the permissions of the item before performing the delivery. The following error message is returned if the object is no-transferable: `transfer permission not set`

This does not apply to folders. An empty folder is delivered if no transferable items are found.

## Comments

* The inventory is loaded each time your bot restarts. Allow about 60 seconds for the inventory to completely load.
* The bot automatically recognizes inventory folders and delivers them accordingly.
* The command pauses for about 15 seconds if the object UUID does not exist in the bot's inventory. To avoid this, make sure you are using correct UUIDs.

## Examples

```javascript
Bot.giveInventory(avatar, object)
  .then(function(result) {
    if (result.success) {
      console.log("The inventory item was sent.");
    } else {
      console.log("Error executing giveInventory: " + result.error);
    }
  });
```