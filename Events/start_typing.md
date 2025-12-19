# start_typing

Fires when another avatar starts typing in IM to the bot.

```javascript
Bot.on("start_typing", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `start_typing` |
| speaker_name | The name of the sender |
| speaker_uuid | The UUID of the sender |
| bot_slname | The name of the bot |
| bot_uuid | The UUID of the bot |

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

## Example

```javascript
Bot.on("start_typing", (event) => {
  console.log(`${event.speaker_name} started typing`);
});

console.log("Bot is listening, IM something");
```