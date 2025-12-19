# startTyping

Sends the "typing" indicator in chat to a specific user.

```javascript
Bot.startTyping(uuid, delay);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `uuid` | yes | The UUID of the user to send the "typing" indicator to. |
| `delay` | optional | Duration (in seconds) for how long the "typing" indicator stays active. Defaults to 15 seconds. |

# Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

# Example

```javascript
Bot.startTyping("1fd5b697-604c-4e34-91f9-f5c98cc46fa3", "20");
```