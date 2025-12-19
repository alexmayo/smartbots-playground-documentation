# inventory_offer

Fires when the bot receives an inventory offer.

```javascript
Bot.on("inventory_offer", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `inventory_offer` |
| item_type | The type of the inventory item (e.g. Notecard, Object, Landmark, etc.) |
| folder | The inventory folder UUID this item will go to |
| sender_type | The type of the sender (`AGENT` or `OBJECT`) |
| sender_name | The name of the sender |
| sender_uuid | The UUID of the sender |
| item_name | The name of the offered item |
| object_id | The inventory UUID of the item being offered |
| item_creator | The UUID of the creator of the inventory item |
| session | The session UUID used to accept the item |

## Example

```javascript
Bot.on("inventory_offer", function(event) {
  console.log(event.sender_name + " sent me a " + event.item_type + " with the name:\n" + event.item_name);
});

console.log("Bot is listening to inventory offers");
```