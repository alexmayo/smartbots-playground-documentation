# regionRestart

Queries to restart the current region of the bot.

```javascript
Bot.regionRestart(delay);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `delay` | optional | Delay before restart in seconds. Default is 120, minimum is 30, maximum is 240. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Permissions

The bot must be an **Estate Manager** of the current region.

## Examples

See the complex **Region Restart** script in the Examples section.