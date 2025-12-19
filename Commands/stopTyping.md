# stopTyping

Stops sending the "typing" indicator in chat to a specific user.

```javascript
Bot.stopTyping(uuid);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `uuid` | yes | The UUID of the user to stop sending the "typing" indicator to. |

# Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

# Example

```javascript
Bot.stopTyping("1fd5b697-604c-4e34-91f9-f5c98cc46fa3");
```