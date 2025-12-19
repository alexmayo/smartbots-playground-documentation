# getLocation

Returns the current location of the bot.

```javascript
await Bot.getLocation();
```

## Input

This function does not require any arguments.

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |
| `online` | boolean | Bot online flag |
| `region` | string | Bot region name |
| `position` | object | Current bot position (rounded to integer) |
| `exactPosition` | object | Exact bot position (with decimals) |

**Example of** `**position**`**:**

```json
{
  "x": 100,
  "y": 110,
  "z": 20
}
```

**Example of** `**exactPosition**`**:**

```json
{
  "x": 100.01,
  "y": 109.65,
  "z": 20.4
}
```

## Details

* This command returns the bot's position in real time. Use it to track the actual position of the bot.
* The `Bot.status()` command also returns the location, but the data may be cached for up to 30 seconds.
* The `position` field is a rounded version of `exactPosition`, added for convenience to avoid manual rounding.

### Calling when offline

If `getLocation()` is called when the bot is offline:

* `online` will be `false`
* `region` will be an empty string
* All coordinates (`x`, `y`, `z`) will be `null`

## Examples

```javascript
const loc = await Bot.getLocation();
if (loc.region == "DuoLife") {
  console.log("Wow, I'm in SmartBots region now!");
  console.log(loc);
}
```

### Example output

```json
{
  "online": true,
  "region": "DuoLife",
  "position": {
    "x": 230,
    "y": 78,
    "z": 32
  },
  "exactPosition": {
    "x": 229.6,
    "y": 77.69,
    "z": 32.1
  }
}
```