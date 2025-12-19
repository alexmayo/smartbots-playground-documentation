# acceptInventoryOffer

Accept (or reject) an inventory offer sent by another avatar or in-world script.

```javascript
Bot.on("inventory_offer", (event) => {
  Bot.acceptInventoryOffer(
    event.sender_type, 
    event.object_id, 
    event.sender_uuid, 
    event.folder, 
    event.session, 
    true
  );
});
```

See the `[inventory_offer](./../Events/inventory_offer.md)` event for details.

## Input

| Variable | Required | Description |
|----|----|----|
| `sender_type` | yes | Who sent the inventory (agent or in-world script) |
| `object_id` | yes | Inventory UUID of the item being offered |
| `sender_uuid` | yes | UUID of the sender |
| `folder` | yes | Inventory folder UUID this item goes to |
| `session` | yes | Session UUID from the event |
| `accept` | yes | `true` to accept the item, `false` to reject |

## Output

| Field | Type | Description |
|----|----|----|
| `success` | bool | true if command completed successfully |
| `error` | string | error string if command has failed |