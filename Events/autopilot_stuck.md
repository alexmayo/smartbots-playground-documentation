# autopilot_stuck

Fires when the bot's autopilot gets stuck and gives up moving further.

```javascript
Bot.on("autopilot_stuck", function(event) { ... });
```

See the `[Bot.walkTo()](./../Commands/walkTo.md)` command for autopilot usage.

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `autopilot_stuck` |
| bot_name | The name of the bot |
| endPoint | The bot's planned destination point `{ X, Y, Z }` |
| actualPoint | The bot's actual location `{ X, Y, Z }` |

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

## Example

```javascript
console.log(`${process.name} started`);

Bot.on("autopilot_stuck", (event) => {
  console.log(`Autopilot stuck: ${JSON.stringify(event, null, 2)}`);
});
```

### Example Output

```json
{
  "name": "autopilot_stuck",
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