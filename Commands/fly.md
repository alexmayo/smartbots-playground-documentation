# fly

Starts or stops flying.

```javascript
Bot.fly(enableFlying);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `enableFlying` | yes | Boolean — `true` to start flying, `false` to stop |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Examples

```javascript
// Start flying
Bot.fly(true);

// Wait 5s
await process.sleep(5_000);

// Stop flying
Bot.fly(false);

// Gracefully exit the test script
process.exit();
```