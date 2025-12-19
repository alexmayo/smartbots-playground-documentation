# inviteGroup

Sends a group invitation to a specific resident.

```javascript
Bot.inviteGroup(avatar, groupuuid, roleuuid, check_membership);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `avatar` | yes | The UUID of the resident |
| `groupuuid` | yes | The UUID of the group |
| `roleuuid` | yes | The UUID of the group role (`NULL_KEY` for "Everyone") |
| `check_membership` | optional | Set to `1` if you want to ignore existing group members (see comments below) |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Comments

### Ignoring existing group members

It is possible to ignore existing group members and not invite them again by setting `check_membership` to `1`.


:::info
**Important:** The bot reloads the list of group members every 10 minutes.\nIf a resident (1) leaves the group and then (2) tries to rejoin immediately, the bot may still think they are a member — in this case, the invitation will be discarded.

:::