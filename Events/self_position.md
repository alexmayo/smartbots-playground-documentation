# self_position

Fires when the bot's in-world location, position, or heading changes.

```javascript
Bot.on("self_position", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `self_position` |
| region | The name of the region the bot is currently in |
| heading | The direction (in degrees) the bot is facing |
| bot_uuid | The UUID of the bot |
| active_group | The UUID of the bot's active group |
| position | The current position of the bot (`X`, `Y`, `Z`) |

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

The event fires when the bot's position and/or view direction changes. The view direction change threshold is **5 degrees** — you won't get a notification if the bot turns less than that.

The event is usually sent in real-time but can be postponed to prevent flooding your script with `self_position` events.

## Example

```javascript
console.log(`${process.name} started`);

Bot.on("self_position", (event) => {
  console.log(`self position event:`, event);
});
```