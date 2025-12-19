# say

Says a message over a specific chat channel.

```javascript
Bot.say(channel, message);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `channel` | yes | The channel to send the message over (`0` = public chat). |
| `message` | yes | The message to send. |

# Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

# Example

```javascript
Bot.say(0, "Hello World!");
```