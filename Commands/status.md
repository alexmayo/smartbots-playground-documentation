# status

Returns the online status of the bot.

```javascript
await Bot.status();
```

Related faster commands:

* `[Bot.getLocation()](./getLocation.md)` — for a bot's location (region and/or coordinates)
* `[Bot.isOnline()](./isOnline.md)` — for bot online status

# Input

This command does not require any parameters.

# Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |
| `status` | string | Current online status of the bot (see **Details**) |
| `online` | string | `"1"` if bot is online, `"0"` otherwise |
| `slname` | string | Full Second Life name of the bot |
| `uuid` | string | Bot avatar UUID |
| `location` | string | Current bot location if the bot is online (`Region/X/Y/Z`) — legacy (see **Bot location** below) |


:::info
Subsequent `status` calls may be cached for up to 30 seconds.

:::

# Bot location

`Bot.status()` returns the bot's location (`location`) for compatibility reasons only.

If you need real-time data, it is recommended to use:

* `[Bot.getLocation()](./getLocation.md)` — to retrieve real-time bot location.
* `[Bot.isOnline()](./isOnline.md)` — to retrieve real-time bot online status.

`Bot.status()` results may be cached (see note above).

# Details

The following statuses can be returned:

* `ONLINE` — the bot is online
* `PRE-CONNECTING` — the bot is preparing to log in and waiting for the SL login server response
* `CONNECTING` — the SL login server is logging the bot in
* `LOGGED OUT` — the bot has logged out gracefully (by the owner's command)
* `OFFLINE` — the bot cannot be contacted (unexpected; usually occurs when SmartBots servers are restarting)

# Example

```javascript
const status = await Bot.status();
console.log("My status is:", status);
```