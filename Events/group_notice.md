# group_notice

Fires when the bot receives a group notice.

```javascript
Bot.on("group_notice", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `group_notice` |
| group_name | The name of the group |
| group_uuid | The UUID of the group |
| speaker_name | The name of the sender |
| speaker_uuid | The UUID of the sender |
| subject | The subject of the notice |
| message | The message of the notice |
| attachment | The type of attachment included in the notice (`Object`, `Notecard`, `Landmark`, `Texture`) |

## Example

```javascript
Bot.on("group_notice", function(event) {
  console.log(event.group_name + ": " + event.speaker_name + " sent notice:\n message: " + event.message + "\n subject: " + event.subject);
});

console.log("Bot is listening to group notices.");
```