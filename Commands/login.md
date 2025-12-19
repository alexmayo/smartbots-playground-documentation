# login

Initiates the bot login sequence.

```javascript
Bot.login(location);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `location` | optional | The initial location to log in to. Leave blank to log in at the previous location.<br><br>Format: Region name/X/Y/Z<br>Use `"HOME"` instead of a location to send the bot home. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Examples

```javascript
Bot.login("DuoLife/206/36/94");
```