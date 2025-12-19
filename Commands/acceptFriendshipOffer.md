# acceptFriendshipOffer

Accept (or reject) a friendship offer sent by another avatar.

```javascript
Bot.on("friendship_offer", (event) => {
  Bot.acceptFriendshipOffer(event.avatar_uuid, event.session_id, true);
});
```

See the `[friendship_offer](./../Events/friendship_offer.md)` event for details.

## Input

| Variable | Required | Description |
|----|----|----|
| `avatar_uuid` | yes | Sender avatar UUID |
| `session_id` | yes | Session UUID from the event |
| `accept` | yes | `true` to accept the offer, `false` to reject |

## Output

| Field | Type | Description |
|----|----|----|
| `success` | bool | true if command completed successfully |
| `error` | string | error string if command has failed |

## Example

```javascript
Bot.on("friendship_offer", async function(event) {
  console.log("Got friendship offer from: " + event.avatar_name + "\n\nAccepting now.");
  let response = await Bot.acceptFriendshipOffer(event.avatar_uuid, event.session_id, true);
  if(response.success) {
    console.log("Accepted the friendship Offer");
  } else {
    console.log("Rejected the friendship Offer");
    console.error("Error: " + response.error);
  }
});

console.log("Bot is listening, friendship offers");
```