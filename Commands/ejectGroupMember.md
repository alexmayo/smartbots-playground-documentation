# ejectGroupMember

Ejects residents from the group.

```javascript
Bot.ejectGroupMember(avatar, groupuuid);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `avatar` | yes | The UUID of the resident |
| `groupuuid` | yes | The UUID of the group |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Comments

If you are using a custom role (other than "Everyone") you need additional abilities for your bot. [Read this](./../../Information/Inviting%20and%20ejecting%20from%20custom%20role.md) for details.