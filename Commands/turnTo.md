# turnTo

Turns the bot to face a specific direction (heading), measured in degrees.

```javascript
await Bot.turnTo(90); // Turn east
```

## Input

| Variable | Required | Description |
|----|----|----|
| `deg` | yes | Desired direction in degrees (0–360).0 = North90 = East180 = South270 = West |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Comments

This command rotates the bot to a specific **absolute direction** (not relative). You can use it to face someone, turn toward a specific location, or align for scripted behaviors.

Due to limitations in Second Life:

* SL will not rotate the avatar if the direction change is less than 20°. To counter this, SmartBots briefly moves the bot to force a heading update.
* Final heading may be off by up to 5°, depending on the region and timing.

# Example

```javascript
Bot.on("after_login", async function(event) {
  console.log("Turning bot to face South...");
  const result = await Bot.turnTo(180);

  if (result.success) {
    console.log("Turned to face South.");
  } else {
    console.error("Failed to turn:", result.error);
  }
});
```