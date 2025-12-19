# listInventory

Returns an inventory list of the given folder.

```javascript
Bot.listInventory(folderUUID).then(function(result) { ... });
```

## Input

| Variable | Required | Description |
|----|----|----|
| `uuid` | yes | The UUID of the folder. Leave blank to retrieve the root folder contents. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |
| `list` | Array | Array containing the folder's items. Each item has the following structure: |

```json
{
  "type": "object",
  "name": "Inventory item name",
  "inventoryUUID": "UUID of the inventory item",
  "assetUUID": "UUID of the asset in SL",
  "flags": "WORN", // if item is currently worn
  "permissions": {
    "mod": true,
    "copy": true,
    "transfer": false
  },
  "nextPermissions": {
    "mod": true,
    "copy": false,
    "transfer": true
  }
}
```

### Item type

A string indicating the item kind: `"folder"`, `"object"`, `"notecard"`, `"clothing"`, etc.

### Permissions object

Describes whether the bot can modify, copy, or transfer an item:

```json
{
  "mod": true,
  "copy": true,
  "transfer": false
}
```

## Comments

### Useful folders

To determine what your bot is currently wearing, locate the **"Current Outfit"** folder at the root of the inventory.

### Inventory-ID vs Asset-ID

There's an important distinction:

* **Inventory ID** – the unique identifier of the object in the bot's personal inventory.
* **Asset ID** – the global identifier of the object in Second Life's asset database.

You can have two identical textures with different Inventory IDs but the same Asset ID.

**Rules of thumb:**

* When rezzing an item, use its **Inventory ID**.
* When a script sets a texture, it uses the **Asset ID**, since scripts access assets globally.

## Examples

See the [example script](./../Examples/Listing%20worn%20items.md) in the Playground Examples section.