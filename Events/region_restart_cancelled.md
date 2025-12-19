# region_restart_cancelled

Fires when the bot receives a region restart cancellation notification.

```javascript
Bot.on("region_restart_cancelled", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `region_restart_cancelled` |
| bot_uuid | The UUID of the bot which receives the notification |
| message | The message of the region restart cancellation |
| region_name | The name of the region |

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

## Example

```javascript
console.log(`${process.name} started`);

Bot.on("region_restart_cancelled", (event) => {
  console.log(`Region restart cancelled:`, event);
});
```