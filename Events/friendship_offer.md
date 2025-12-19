# friendship_offer

Fires when the bot receives a friendship offer.

```javascript
Bot.on("friendship_offer", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| avatar_name | The name of the sender |
| avatar_uuid | The UUID of the sender |
| message | The text message sent along with the offer |
| session_id | The session UUID to accept the offer |

See also: Use `[acceptFriendshipOffer](./../Commands/acceptFriendshipOffer.md)` to accept an offer.

## Example

```javascript
Bot.on("friendship_offer", function(event) {
  console.log(`${event.avatar_name} offers friendship and says: ${event.message}`);
});

console.log("Bot is listening to friendship offers");
```