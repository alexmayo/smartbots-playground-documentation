# instant_message

Fires when the bot receives a message from another avatar or in-world object.

```javascript
Bot.on("instant_message", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `instant_message` |
| speaker_type | The sender of the message (`AVATAR` or `OBJECT`) |
| speaker_name | The name of the sender |
| speaker_uuid | The UUID of the sender |
| object_uuid | The UUID of the object |
| speaker_distance | The distance to the sender in metres (only for `AVATAR`) |
| speaker_x | The x position in the region of the sender (only for `AVATAR`) |
| speaker_y | The y position in the region of the sender (only for `AVATAR`) |
| speaker_z | The z position in the region of the sender (only for `AVATAR`) |
| message | The text of the message |

### Speaker distance and coordinates

This event also returns `speaker_distance`, `speaker_x`, `speaker_y`, and `speaker_z` so that you can determine the sender's position. These values may return `NULL` if the bot or speaking avatar has only just appeared in-world.

## Example

```javascript
Bot.on("instant_message", function(event) {
  console.log(event.speaker_name + " says:\n" + event.message);
});

console.log("Bot is listening, IM something");
```