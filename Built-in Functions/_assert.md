# _assert

Logs data to the error log if the assertion is false.

```javascript
var online = await Bot.isOnline();
_assert(online, "Bot is not online");
```

# Input

| Variable | Required | Description |
|----|----|----|
| `assertion` | yes | Any boolean expression. |
| `errorMessage` | yes | The message to send to the error log if `assertion` is false. |

# Output

This function does not return anything.

# Comments

If the `assertion` evaluates to `false`, the provided `errorMessage` is logged to the error log.\nUseful for debugging and validating assumptions during bot script execution.

# Examples

```javascript
var online = await Bot.isOnline();
_assert(online, "Bot is not online");
```