# setGroupRole

Assigns a group member to a specific role.

```javascript
Bot.setGroupRole(avatar_uuid, group_uuid, role_uuid)
  .then(function(result) {
    if (result.success) { console.log("Role revoked"); }
  });
```

# Input

| Variable | Required | Description |
|----|----|----|
| `avatar_uuid` | yes | The UUID of the avatar to assign to the specified role. |
| `group_uuid` | yes | The UUID of the group. |
| `role_uuid` | yes | The UUID of the group role. The "Everyone" role is `00000000-0000-0000-0000-000000000000`. |

# Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

# Comments

Ensure your bot has sufficient rights to assign or revoke members from group roles.

Check the [complex example](./../Examples/Setting%20&%20revoking%20group%20roles.md) for detailed usage.