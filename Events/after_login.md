# after_login

Fires when the bot successfully logs into Second Life.

```javascript
Bot.on("after_login", function(event) { ... });
```

## Reference

This event has no properties.

## Example

```javascript
Bot.on("after_login", function(event) {
  console.log("Bot is successfully logged in!");
});
```