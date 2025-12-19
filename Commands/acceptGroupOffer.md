# acceptGroupOffer

Accept (or reject) a group invitation sent by another avatar.

```javascript
Bot.on("group_offer", (event) => {
  Bot.acceptGroupOffer(event.avatar_uuid, event.session_id, true);
});
```

See the `[group_offer](./../Events/group_offer.md)` event for details.

## Input

| Variable | Required | Description |
|----|----|----|
| `avatar_uuid` | yes | Sender avatar UUID |
| `session_id` | yes | Session UUID from the event |
| `accept` | yes | `true` to accept the invitation, `false` to reject |

## Output

| Field | Type | Description |
|----|----|----|
| `success` | bool | true if command completed successfully |
| `error` | string | error string if command has failed |