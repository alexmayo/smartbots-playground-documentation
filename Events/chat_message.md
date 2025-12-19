# chat_message

Fires when the bot receives a message in the local chat.

```javascript
Bot.on("chat_message", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event |
| speaker_type | The sender of the message. Can be `AGENT` or `OBJECT` |
| speaker_name | The name of the sender |
| speaker_uuid | The UUID of the sender |
| speaker_owner | The UUID of the owner of the sender object |
| speaker_distance | The distance to the sender in metres (works only if `speaker_type` is `AGENT`) |
| speaker_x | The x position in the region of the sender (works only if `speaker_type` is `AGENT`) |
| speaker_y | The y position in the region of the sender (works only if `speaker_type` is `AGENT`) |
| speaker_z | The z position in the region of the sender (works only if `speaker_type` is `AGENT`) |
| message | The text of the message |
| chat_type | One of the following: `Normal`, `Whisper`, `Shout`, `OwnerSay` |
| own_message | `true` if the message was said by the bot itself |

## Important note

The bot **does** hear what it says, so you will get a `chat_message` event when the bot says something in local chat.\nMake sure to ignore the bot's own messages (especially for auto-responders).

## Speaker distance and coordinates

This event also returns `speaker_distance`, `speaker_x`, `speaker_y`, and `speaker_z` so you can determine the speaker's position.\nIt's important to note that these parameters may return `null` if the bot or speaking avatar has only just appeared in-world.

## Example

```javascript
Bot.on("chat_message", function(event) {
  // Ignore own messages
  if(event.own_message) { return; }

  console.log(event.speaker_name + " says: \n" + event.message);
});

console.log("Bot is listening for local chat");
```