# avatar_tracker_update

Fires when a tracked avatar changes position, logs out, teleports, or becomes visible again.

Requires `[Bot.trackAvatars()](./../Commands/trackAvatars.md)` to be called first.

```javascript
Bot.on("avatar_tracker_update", function(event) { ... });
```

See the `[Bot.trackAvatars()](./../Commands/trackAvatars.md)` command for usage.

## Reference


:::warning
Make sure `Bot.on("avatar_tracker_update", ...)` is defined **before** calling `[Bot.trackAvatars()](./../Commands/trackAvatars.md)` to avoid missing early updates.

:::

This event comes with the following event object:

| Variable | Description |
|----|----|
| `name` | The name of the event — always `avatar_tracker_update` |
| `bot_slname` | The Second Life name of the bot |
| `bot_uuid` | UUID of the bot |
| `avatar_name` | The tracked avatar's Second Life name (may be null if unknown) |
| `avatar_uuid` | UUID of the tracked avatar |
| `region` | The region name the avatar is currently in |
| `regionHandle` | 64-bit handle of the region |
| `position` | Avatar's current position (`X`, `Y`, `Z`) in region coordinates, or `null` if not visible |
| `velocity` | Avatar's movement speed vector (`X`, `Y`, `Z`) in m/s |
| `heading` | Direction the avatar is facing (radians) |
| `sitting` | `true` if the avatar is sitting, otherwise `false` |
| `timestamp` | Internal SmartBots timestamp of the update |
| `event_version` | Format version of the event payload |
| `version` | Bot client version string |

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

## Example

```javascript
Bot.on("avatar_tracker_update", (event) => {
  if (event.position) {
    Bot.say(0, `${event.avatar_name} is at X: ${event.position.X.toFixed(2)}, Y: ${event.position.Y.toFixed(2)}, Z: ${event.position.Z.toFixed(2)}`);
  } else {
    Bot.say(0, `${event.avatar_name} is no longer visible.`);
  }
});

//When the bot logs in, or script starts
Bot.on("after_login", (event) => {
	//Start tracking the avatar
	Bot.trackAvatars("4d9ce772-d3ee-4cce-9555-bfb06ffcb228");
});
```

### Example Output

```json
{
  "name":"avatar_tracker_update",
  "bot_slname":"OneSmartBot Resident",
  "heading":-0.8756585,
  "bot_uuid":"bd67863e-b273-4c3b-8ae5-dd8f61229280",
  "region":"DuoLife",
  "sitting":false,
  "avatar_name":"Alexander Pixels",
  "avatar_uuid":"4d9ce772-d3ee-4cce-9555-bfb06ffcb228",
  "velocity":{
    "X":0,
    "Y":0,
    "Z":0
  },
  "position":{
    "X":140.54955,
    "Y":38.20348,
    "Z":22.085785
  },
  "timestamp":63896593110303,
  "event_version":3,
  "regionHandle":849922488517376,
  "version":"131.01.00"
}
```

Fires when a tracked avatar changes position, logs out, teleports, or becomes visible again.

Requires `Bot.trackAvatars()` to be called first.