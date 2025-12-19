# isMyManager

Returns `true` if the specified avatar is a Trusted Manager for the bot.

```javascript
const res = await Bot.isMyManager("slnameOrUUID");
console.log("Is Bot Manager:", res);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `slName or UUID` | yes | The avatar's Second Life name or UUID |

## Output

| Variable | Type | Description |
|----|----|----|
| `return value` | boolean | `true` if the resident is a trusted manager of the bot |

## Examples

```javascript
Bot.on("chat_message", async function (event) {
  let isManager = await Bot.isMyManager(event.speaker_name);
  if (isManager) {
    console.log(`Message from Trusted Manager`);
  }
});
```