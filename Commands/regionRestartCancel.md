# regionRestartCancel

Cancels a pending restart of the current region.

```javascript
Bot.regionRestartCancel();
```

## Input

This command does not require any parameters.

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Permissions

The bot must be an **Estate Manager** of the current region.

## Examples

See the [complex script](./../Examples/Region%20restart.md) in the Examples section.