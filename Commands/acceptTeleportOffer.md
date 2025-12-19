# acceptTeleportOffer

Accept (or reject) a teleport offer sent by another avatar.

```javascript
Bot.on("teleport_offer", (event) => {
  Bot.acceptTeleportOffer(event.avatar_uuid, event.session_id, true);
});
```

See the `[teleport_offer](./../Events/teleport_offer.md)` event for details.

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

## Comments

* Bot cannot reject teleport offers from its owner.

## Example

```javascript
Bot.on("teleport_offer", async function(event) {
  console.log("Got teleport offer from: " + event.avatar_name + "\n\nAccepting now.");
  let response = await Bot.acceptTeleportOffer(event.avatar_uuid, event.session_id, true);
  if(response.success) {
    console.log("Accepted the Teleport Offer");
  } else {
    console.log("Rejected the Teleport Offer");
    console.error("Error: " + response.error);
  }
});

console.log("Bot is listening, teleport offers");
```