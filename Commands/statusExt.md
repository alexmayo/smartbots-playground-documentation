# statusExt

Returns the online status of the bot.

```javascript
const res = await Bot.statusExt();
console.log("Status:", JSON.stringify(res, null, 2));
```

# Input

This command does not require any parameters.

# Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |
| `status` | object | Contains various information about the bot status (see **Details** below). |


:::info
Subsequent command calls may be cached for up to 60 seconds. Use the `status` command to get a faster refresh rate.

:::

# Details

The `status` field of the response provides detailed information about the bot:

```json
{
  // Bot name
  "name": "Fashion Firethorn",
  // Bot UUID
  "UUID": "fc417c00-71ae-4427-a9dd-eed32a3e49de",

  // = Connection status
  // Is bot online
  "online": true,
  // Is bot connecting to Second Life right now
  "connecting": false,

  // In-world status
  // Avatar position
  "position": {
    "Z": 33.377563,
    "X": 234.81233,
    "Y": 111.23107
  },
  // Avatar heading (the view direction), radians
  "heading": -3.0020456,

  // Current region (sim) name
  "regionName": "DuoLife",
  // Current region ID
  "regionHandle": 849922488517376,
  // Current parcel name
  "parcelName": "SmartBots: Second Life bots for L$79 / Inviter bot + notices",
  // Current parcel ID
  "parcelID": 150,

  // Bot OS version
  "version": "91.00.00"
}
```