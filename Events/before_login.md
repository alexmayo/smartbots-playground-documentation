# before_login

Fires when the bot is going to log in to Second Life.

```javascript
Bot.on("before_login", function(event) { ... });
```

## Reference

This event has no properties.

## Comments

This event fires right before the bot tries to log in to Second Life.\nIt is a pair to the `after_login` event — but they are **not the same**: remember that the login procedure may fail (for example, due to an incorrect password).

## Example

```javascript
Bot.on("before_login", function(event) {
  console.log("Bot is going to login. Let's see if the password is right!");
});
```