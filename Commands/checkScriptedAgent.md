# checkScriptedAgent

Returns if the resident is a scripted agent known by SmartBots. This includes all SmartBots bots and other residents our system considers bots or scripted agents.

```javascript
const res = await Bot.checkScriptedAgent("slnameOrUUID");
console.log("Is Bot Scripted Agent:", res);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `slName or UUID` | yes | The Avatar SL Name or UUID |

## Output

| Return value | Description |
|----|----|
| (boolean) | true if resident is a bot |

## Examples

```javascript
Bot.on("chat_message", async function (event) {
  let isBot = await Bot.checkScriptedAgent(event.speaker_name);
  if (isBot) {
    console.log(`Message from Bot`);
  }
});
```