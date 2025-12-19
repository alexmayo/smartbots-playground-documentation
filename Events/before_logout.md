# before_logout

Fires when the bot is going offline.

```javascript
Bot.on("before_logout", function(event) { ... });
```

## Reference

This event has no properties.

## Comments

This event fires right before the bot goes offline.\nThe logout process starts immediately, so you **cannot interact with Second Life** (e.g. send IMs) within this event.\nHowever, you can still use `[console.log()](./../Built-in%20Functions/console.log.md)` and all Bots Playground functionality.

## Example

```javascript

Bot.on("before_logout", function(event) {
  console.log("I'm going offline. See you later.");
});
```