# balance_changed

Fires when the bot receives or pays money.

```javascript
Bot.on("balance_changed", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `balance_changed` |
| amount | The amount which was paid or received |
| direction | The direction of the money flow. Can be:<br>`"INITIAL"`: bot has logged in, balance is known now<br>`"INCOMING"`: money has arrived<br>`"OUTGOING"`: money has been sent |
| source | The UUID of the money sender |
| destination | The UUID of the money receiver |
| balance | The current balance after the payment |
| trx_type | The transaction type |
| comment | Transaction comment |
| transaction | Transaction UUID |

## Example

```javascript
Bot.on("balance_changed", function(event) {
  console.log("Balance changed, my new balance is: " + event.balance);
});

console.log("Bot is listening to payments");
```