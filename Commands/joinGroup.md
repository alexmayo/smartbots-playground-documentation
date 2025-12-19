# joinGroup

Tries to join a group by UUID.

```javascript
Bot.joinGroup(groupuuid);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `groupuuid` | yes | The UUID of the group |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Comments

* The group enrollment should be open for the bot to be able to join.
* The group can be hidden from SL search.