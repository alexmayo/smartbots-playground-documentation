# sit

Commands the bot to sit on a specific prim. Allows saving this object as a permanent sitting location.

```javascript
Bot.sit(uuid, save);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `uuid` | yes | The UUID of the object to sit on. Use `"NONE"` instead of a UUID to make the bot stand up. |
| `save` | no | Set this parameter to `1` to save the UUID as a permanent sitting location. The bot will sit on this object after relog, crash, or sim restart. |

# Output

This function does not return anything.