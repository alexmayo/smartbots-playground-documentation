# autopilot_started

Fires when the bot's autopilot starts.

```javascript
Bot.on("autopilot_started", function(event) { ... });
```

See the `[Bot.walkTo()](./../Commands/walkTo.md)` command for autopilot usage.

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `autopilot_started` |
| bot_name | The name of the bot |
| currentPoint | The bot's current location `{ X, Y, Z }` |
| endPoint | The bot's destination point `{ X, Y, Z }` |

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

## Example

```javascript
console.log(`${process.name} started`);

Bot.on("autopilot_started", (event) => {
  console.log(`Autopilot started: ${JSON.stringify(event, null, 2)}`);
});
```

### Example Output

```json
{
  "name": "autopilot_started",
  "bot_slname": "DakotahRaine Resident",
  "bot_uuid": "4f6b8999-14a0-4f50-882d-a764ee913daa",
  "endPoint": {
    "X": 212,
    "Y": 25,
    "Z": 93
  },
  "currentPoint": {
    "X": 203.21446,
    "Y": 36.776222,
    "Z": 93.68485
  }
}
```