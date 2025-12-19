# script_dialog

Fires when the bot receives a scripted dialog with menu buttons.

```javascript
Bot.on("script_dialog", function(event) { ... });
```

Use `[replyDialog](./../Commands/replyDialog.md)` to "click" a required menu button.

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event — in this case `script_dialog` |
| buttons | The selection options (buttons) as an array |
| channel | The channel on which the dialog listens |
| owner_name | The name of the owner of the object that sent the dialog |
| text | The text displayed in the dialog window |
| object_uuid | The UUID of the object that sent the dialog |
| object_name | The name of the object that sent the dialog |

## Example

```javascript
Bot.on("script_dialog", function(event) {
  console.log(
    "Got a dialog:\n" +
    event.text + "\n\n" +
    "channel: " + event.channel + "\n" +
    "buttons:\n" + event.buttons.join("\n")
  );
});
```