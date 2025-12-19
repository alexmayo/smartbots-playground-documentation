# replyDialog

Virtually "presses" a pop-up dialog button displayed by an in-world script.

```javascript
Bot.replyDialog(channel, object, button);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `channel` | yes | The dialog channel (can be a positive or negative value). |
| `object` | yes | The UUID of the object that sent the dialog. |
| `button` | yes | The text of the dialog button to press. |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

## Example

```javascript

Bot.on("script_dialog", function(event) {
  Bot.replyDialog(event.channel, event.object_uuid, event.buttons[0]);
  console.log("Got a dialog and answered with the first button: " + event.buttons[0]);
});
```