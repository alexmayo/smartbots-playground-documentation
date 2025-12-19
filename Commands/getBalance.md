# getBalance

Retrieves the current bot's L$ balance.

```javascript
const result = await Bot.getBalance();
console.log("I have L$" + result.balance);
```

## Input

This function does not require any arguments.

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |
| `balance` | number | The current bot L$ balance |

## Comments

This function can be used with a callback:

```javascript
Bot.getBalance(function(result) {
  console.log("I have L$" + result.balance);
});
```

## Examples

For a comprehensive balance management script, check the [example](./../Examples/Working%20with%20L$.md).