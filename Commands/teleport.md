# teleport

Teleports the bot to a specific location.

```javascript
Bot.teleport(location);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `location` | yes | Address of the new location in the format: `Region name/X/Y/Z`. Use `"HOME"` instead of a location to send the bot home. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Examples

Teleport the bot to the SmartBots office:

```javascript
Bot.teleport("DuoLife/128/128/20");
```

Teleport the bot to its home location:

```javascript
Bot.teleport("HOME");
```