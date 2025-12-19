# teleport_offer

Fires when the bot receives a teleport offer from another avatar.

```javascript
Bot.on("teleport_offer", function(event) { ... });
```

Use `[acceptTeleportOffer](./../Commands/acceptTeleportOffer.md)` to accept or reject a teleport offer.

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| avatar_name | Sender's SL name |
| avatar_uuid | The UUID of the sender |
| message | Teleport offer message |
| slurl | The teleport location |

## Example

```javascript
Bot.on("teleport_offer", function(event) {
  console.log("Got teleport offer from: " + event.avatar_name);
});

console.log("Bot is listening, teleport offers");
```