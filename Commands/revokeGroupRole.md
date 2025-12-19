# revokeGroupRole

Removes a group member from a specific role.\nAlso see the `[setGroupRole](./setGroupRole.md)` function.

```javascript
Bot.revokeGroupRole(avatar_uuid, group_uuid, role_uuid)
  .then(function(result) {
    if (result.success) { console.log("Role revoked"); }
  });
```

## Input

| Variable | Required | Description |
|----|----|----|
| `avatar_uuid` | yes | The UUID of the avatar to remove from the role. |
| `group_uuid` | yes | The UUID of the group. |
| `role_uuid` | yes | The UUID of the group role. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Comments

Ensure your bot has sufficient rights to assign or revoke members from group roles.

Check the [complex example](./../Examples/Setting%20&%20revoking%20group%20roles.md) for detailed usage.