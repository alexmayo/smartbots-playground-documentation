# trackAvatars

Begins tracking the real-time position of one or more avatars.

```javascript
Bot.trackAvatars("4d9ce772-d3ee-4cce-9555-bfb06ffcb228");
```

## Input

| Variable | Required | Description |
|----|----|----|
| `avatars` | yes | One or more UUIDs, separated by spaces. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Comments

After calling this command, your script will start receiving `avatar_tracker_update` events.

See the avatar tracking example for usage.

### Important Notes


:::warning
Always call `Bot.trackAvatars()` inside the `after_login` event, as tracking stops after bot logs out.

:::

* Only avatars in the same region as the bot can be tracked.
* You can track up to 8 avatars at once.
* Always define your event listeners before calling `Bot.trackAvatars()` to avoid missing updates.

## Examples

This script says the target avatar's position in local chat, whenever it changes.

```javascript
// Tracking update received
Bot.on("avatar_tracker_update", (event) => {
	Bot.say(0, event.avatar_name + " is at " + JSON.stringify(event.position));
});

//When the bot logs in, or script starts
Bot.on("after_login", (event) => {
	//Start tracking the avatar
	Bot.trackAvatars("4d9ce772-d3ee-4cce-9555-bfb06ffcb228");
});
```