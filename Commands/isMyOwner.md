# isMyOwner

Returns `true` if the specified avatar is the owner of the bot.

```javascript
const res = await Bot.isMyOwner("slnameOrUUID");
console.log("Is Bot Owner:", res);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `slName or UUID` | yes | The avatar's Second Life name or UUID |

## Output

| Variable | Type | Description |
|----|----|----|
| `return value` | boolean | `true` if the resident is the owner of the bot |

## Examples

```javascript

Bot.on("chat_message", async function (event) {
  let isOwner = await Bot.isMyOwner(event.speaker_name);
  if (isOwner) {
    console.log(`Message from Owner`);
  }
});
```