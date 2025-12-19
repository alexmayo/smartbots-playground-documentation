# autopilot_completed

Fires when the bot's autopilot successfully completes its journey.

```javascript
Bot.on("autopilot_completed", function(event) { ... });
```

See the `[Bot.walkTo()](./../Commands/walkTo.md)` command for autopilot usage.

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `autopilot_completed` |
| bot_name | The name of the bot |
| endPoint | The bot's destination point `{ X, Y, Z }` |
| actualPoint | The bot's final location `{ X, Y, Z }` |

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

## Example

```javascript
console.log(`${process.name} started`);

Bot.on("autopilot_completed", (event) => {
  console.log(`Autopilot completed: ${JSON.stringify(event, null, 2)}`);
});
```

### Example Output

```json
{
  "name": "autopilot_completed",
  "bot_slname": "DakotahRaine Resident",
  "bot_uuid": "4f6b8999-14a0-4f50-882d-a764ee913daa",
  "endPoint": {
    "X": 212,
    "Y": 25,
    "Z": 93
  },
  "actualPoint": {
    "X": 203.21446,
    "Y": 36.776222,
    "Z": 93.68485
  }
}
```