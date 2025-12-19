# teleport_status

Fires when the bot teleports, indicating various stages of the teleport.

```javascript
Bot.on("teleport_status", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `teleport_status` |
| bot_name | The name of the bot teleporting |
| message | The status message of the teleport |
| status | The status of the teleport (`Start`, `Progress`, `Finished`) |
| bot_uuid | The UUID of the bot teleporting |
| location | The current location of the bot |

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

## Example

```javascript
console.log(`${process.name} started`);

Bot.on("teleport_status", (event) => {
  console.log(`teleport status event: `, event);
});
```