# scanNearbyAvatars

Scans the current region for nearby avatars.

```javascript
const result = await Bot.scanNearbyAvatars();
```

# Input

This command does not require any parameters.

# Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |
| `avatars` | array | An array containing avatars detected in the region. See **Response details** for more information. |

# Response details

The `avatars` field of the response contains an array of avatar data:

```json
{
  "name": "GrrrillaBongo Resident",
  "UUID": "d8e20552-ca84-4c42-b8d3-e8fa5fbdcc6b",
  "parcelID": 177,
  "sitting": false,
  "position": {
    "X": 110,
    "Y": 75,
    "Z": 32
  },
  "localPosition": {
    "X": 110,
    "Y": 75,
    "Z": 32
  },
  "heading": 0,
  "localHeading": 0,
  "distance": 129.97195,
  "seenSince": "2022-10-18T12:36:58.2626463Z",
  "seenSeconds": 123
}
```

# Details

The `seenSince` value indicates when the bot first detected a specific avatar after running `scanNearbyAvatars`. For example:


1. Bot logs in and runs idle for 1 hour.
2. Script calls `scanNearbyAvatars` — bot sees **Guest1**, sets `seenSince` to `"2022-10-18 13:00"`.
3. Five minutes later, script calls `scanNearbyAvatars` again — bot now also sees **Guest2**, whose `seenSince` is `"2022-10-18 13:05"`.

Subsequent calls will include:

* Guest1: `seenSince = "2022-10-18 13:00"`
* Guest2: `seenSince = "2022-10-18 13:05"`

`seenSeconds` shows how long (in seconds) the avatar has been visible to the bot (`Now - seenSince`).

# Throttling

The maximum rate for calling `scanNearbyAvatars` is **2 calls per 10 seconds**.\nExcessive requests will return the error:\n`"Frequent API requests throttled"`.

# Data size

This command can return large amounts of data (up to 10 KB or more).\nRemember that `console.log()` can only handle about 4 KB of text output.

To inspect the response safely, use a loop such as:

```javascript
for (const avatar of result.avatars) {
  console.log(`${avatar.name}: seen for ${avatar.seenSeconds} seconds`);
}
```

# Instant message and chat message events

If you're using this command to measure speaker distance, it's more efficient to use the `speaker_distance` property in the `chat_message` or `instant_message` events instead:

```javascript
Bot.on("chat_message", function(event) {
  console.log("Speaker distance: " + event.speaker_distance + "m"); // Speaker distance: 4.88m
});
```

# Examples

See the [nearby avatars script](./../Examples/Scan%20nearby%20avatars.md) in the examples section.