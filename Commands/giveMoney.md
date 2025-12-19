# giveMoney

Commands the bot to send money (L$) to a specific avatar.

```javascript
Bot.giveMoney(avatar, amount, comment);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `avatar` | yes | The avatar UUID |
| `amount` | yes | The amount of money to give |
| `comment` | optional | Text comment for the money transaction |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Examples

For a comprehensive balance management script, see the [example](./../Examples/Working%20with%20L$.md).