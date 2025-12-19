# after_logout

Fires after the bot goes offline.

```javascript
Bot.on("after_logout", function(event) { ... });
```

## Reference

This event has no properties.

## Comments


:::info
Not available for self-hosted QubicBot app yet.

:::

## Example

```javascript
Bot.on("after_logout", function(event) {
  console.log("I went offline. See you later.");
});
```