# group_im

Fires when the bot receives a group chat message.

```javascript
Bot.on("group_im", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `group_im` |
| group_name | The name of the group |
| group_uuid | The UUID of the group |
| speaker_name | The name of the sender |
| speaker_uuid | The UUID of the sender |
| message | The text of the message |

## Example

```javascript
Bot.on("group_im", function(event) {
  console.log(event.group_name + ": " + event.speaker_name + " says:\n" + event.message);
});

console.log("Bot is listening to group chat.");
```