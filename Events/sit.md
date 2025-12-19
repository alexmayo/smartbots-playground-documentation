# sit

Fires when the bot sits on an object.

```javascript
Bot.on("sit", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| sitting | `true` if the bot is seated on the object, `false` if it is standing |
| object_uuid | The UUID of the object the bot is sitting on. `NULL_KEY` if the bot is standing |
| position | An object `{ x, y, z }` representing the sitting position (offset). Empty if `sitting == false` |

## Example

```javascript
Bot.on("sit", function(event) { 
  if (event.sitting) {
    console.log("I'm sitting on the object ", event.object_uuid);
  } else {
    console.log("I'm standing now");
  }
});
```