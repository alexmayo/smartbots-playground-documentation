# activateGroup

Activates a specific group (for example, to get build rights on the parcel).

```javascript
Bot.activateGroup(groupuuid);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `groupuuid` | yes | The UUID of the group to activate |

**Special values:**

* `LAND` — set the group to the current parcel's group (see examples)
* `00000000-0000-0000-0000-000000000000` — remove active group

The bot must already be a member of the group to activate it.

## Output

| Field | Type | Description |
|----|----|----|
| `success` | bool | true if command completed successfully |
| `error` | string | error string if command has failed |

## Examples

Set the active group to match the current parcel's group. This can be used to get rights to rez items:

```javascript
Bot.activateGroup("LAND");
```

Remove active group from the bot (sets the active group to none):

```javascript
Bot.activateGroup("00000000-0000-0000-0000-000000000000");
```