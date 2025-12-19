# takeInworldPrim

Takes (de-rezzes) or copies an in-world prim into the bot's inventory.

```javascript
Bot.takeInworldPrim(operation, objectUUID, folderUUID);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `operation` | yes | One of the following values:<br>•take– to take the object from the world completely<br>•copy – to take a copy of the object |
| `objectUUID` | yes | The UUID of the in-world object |
| `folderUUID` | no | (Optional) UUID of the folder to place the object in. The **Objects** folder is used if not specified. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Comments


:::info
*Not available for self-hosted QubicBot app yet.*

:::

Your bot must have the rights to take or copy the specified object — either by owning it or having sufficient permissions as the owner's friend.

## Example

Take (de-rez) an in-world object to the default ("Objects") folder:

```javascript
Bot.takeInworldPrim("take", "bd36c29f-8a14-4350-b648-3e0f50b6d32a");
```