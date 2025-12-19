# move

Starts or stops bot movement and rotation.

```javascript
Bot.move(instruction, state);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `instruction` | yes | The movement instruction. One of the following:<br>`"FORWARD"` – start/stop forward movement<br>`"BACKWARD"` – start/stop backward movement<br>`"LEFT"` – start/stop turning left<br>`"RIGHT"` – start/stop turning right<br>`"FLY"` – start/stop flying<br>`"STOP"` – stops all movements |
| `state` | yes | The control state of the instruction:<br>`"START"` – starts the instruction<br>`"STOP"` – stops the instruction |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Details

This function allows direct control over the bot's movement.

It may be slightly laggy — for more precise movement, use `[Bot.walkTo()](https://b)` instead.\nFor tracking movement updates, use the `[self_position](./../Events/self_position.md)` event, which reports bot position changes.

## Examples

```javascript
Bot.move("FORWARD", "START");

// Walk forward for 2 seconds

await process.sleep(2_000);

Bot.move("FORWARD", "STOP");
```