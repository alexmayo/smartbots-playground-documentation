# login_error

Fires when the bot is unable to log in to Second Life.

```javascript
Bot.on("login_error", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| reason | The login error text returned by Second Life servers |

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

If the bot logs in for the first time (or due to certain conditions), the `bot_uuid` field may have a zero UUID.

## Example

```javascript

Bot.on("login_error", (event) => {
  console.log("Error logging in:", event.reason);
});

Bot.on("after_login", (event) => {
  console.log("Bot is successfully logged in!");
});

console.log("Waiting for bot to log in");
```