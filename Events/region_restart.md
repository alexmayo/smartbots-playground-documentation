# region_restart

Fires when the bot receives a region restart notification.

```javascript
Bot.on("region_restart", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `region_restart` |
| message | The message of the region restart |
| bot_uuid | The UUID of the bot which receives the notification |
| region_name | The name of the region going to restart |
| time_units | Unit of time in which the region is going to restart (`Seconds`, `Minutes`, or `Unknown`) |
| time_left | Amount of time until region restart based on `time_units` |
| seconds_left | Amount of time until region restart in seconds |

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

* `time_left` contains the time until restart in `time_units`.
* `time_units` are `Seconds` or `Minutes` — `Unknown` is sent if any other unit is received.
* `seconds_left` is always the time until restart in seconds.

## Example

```javascript
console.log(`${process.name} started`);

Bot.on("region_restart", (event) => {
  console.log(`Region restart event:`, event);
});
```