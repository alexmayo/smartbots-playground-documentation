# group_offer

Fires when the bot receives a group invite.

```javascript
Bot.on("group_offer", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `group_offer` |
| avatar_name | The name of the sender |
| avatar_uuid | The UUID of the sender |
| group_name | The name of the group |
| group_uuid | The UUID of the group |
| session_id | The session ID used to accept the invitation |
| system_message | The Second Life system message |

## Example

```javascript
Bot.on("group_offer", function(event) {
  console.log(event.avatar_name + " invited me to group:\n" + event.group_name);
});

console.log("Bot is listening, group invites");
```