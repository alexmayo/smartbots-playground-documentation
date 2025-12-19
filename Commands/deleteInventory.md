# deleteInventory

Commands bot to delete an inventory item.

```javascript
Bot.deleteInventory(uuid);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `uuid` | yes | The inventory UUID of the item. Use the Personal Bot Control Panel to get this UUID. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | true if command completed successfully |
| `error` | string | error string if command has failed |

## Examples

```javascript
Bot.deleteInventory(uuid)
  .then(function(result) {
    if(result.success) {
      console.log("The inventory item was deleted.");
    } else {
      console.log("Error executing deleteInventory: " + result.error);
    }
  });
```