# walkTo

Walk to a position within the current region.

```javascript
Bot.walkTo(x, y, z);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `x` | yes | The X coordinate of the destination point |
| `y` | yes | The Y coordinate of the destination point |
| `z` | yes | The Z coordinate of the destination point |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Details

The bot does not navigate intelligently to the point — instead, it walks directly toward the specified coordinates, pushing through any obstacles along the way, similar to continuously pressing the "arrow up" key.

If the bot gets stuck for 2 seconds (for example, by hitting a wall), the autopilot ends automatically.

You can use the `[fly](./fly.md)` command to start flying and reach higher destination points.

These events indicate the autopilot status:

* `[autopilot_started](./../Events/autopilot_started.md)` — autopilot started
* `[autopilot_completed](./../Events/autopilot_completed.md)` — autopilot reached destination point
* `[autopilot_stuck](./../Events/autopilot_stuck.md)` — autopilot got stuck (and stopped)

# Examples

```javascript
// Bots Playground script: [TEST] Autopilot events (build 1 by Glaznah Gassner)
Bot.on("autopilot_completed", (event) => {
  console.log(`Autopilot completed: ${JSON.stringify(event, null, 2)}`);
});

Bot.on("autopilot_stuck", (event) => {
  console.log(`Autopilot stuck: ${JSON.stringify(event, null, 2)}`);
});

console.log("Script is running, waiting for autopilot events");

// Start autopilot

Bot.walkTo(203, 37, 93);

// Gracefully end test script in 10 seconds

setTimeout(() => process.exit(), 10_000);
```

**Example output:**

```
07/12/2023 13:28:39

Script is running, waiting for autopilot events

07/12/2023 13:28:42

Autopilot completed: {
  "name": "autopilot_completed",
  "bot_slname": "DakotahRaine Resident",
  "bot_uuid": "4f6b8999-14a0-4f50-882d-a764ee913daa",
  "endPoint": {
    "X": 203,
    "Y": 37,
    "Z": 93
  },
  "actualPoint": {
    "X": 203.21898,
    "Y": 36.799942,
    "Z": 93
  }
}
```