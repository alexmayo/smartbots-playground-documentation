# Dialog usage

This script demonstrates the basic usage of `script_dialog` and `replyDialog`.

It sends you an Instant Message (IM) with available dialog options each time your bot receives a dialog menu.\nYou can then reply via IM with the option you want your bot to select.

```javascript
// You should put your avatar name here to ensure you receive dialog options via IM and can respond to them.
var ownerName = "YourName Resident";

var channel;
var objUuid;
var options;
var index;

Bot.on("script_dialog", function(event) {
  channel = event.channel;
  objUuid = event.object_uuid;
  options = event.buttons;
  Bot.im(ownerName, "I just received a dialog, respond to me with the option I should choose:\n\nChannel:" + channel + "\n\nMessage:\n" + event.text + "\n\nOptions:\n" + options.join("\n") + "\nIgnore - Ignores the dialog\n\n(The options are CaSe SeNsItIvE)");
});

Bot.on("instant_message", function(event) {
  if (Array.isArray(options)) {
    if (event.speaker_name == ownerName) {
      if (event.message.toLowerCase() == "ignore") {
        channel = objUuid = options = index = "";
        Bot.im(ownerName, "Dialog ignored successfully.");
      } else {
        index = options.indexOf(event.message);
        if (index != "-1") {
          Bot.replyDialog(channel, objUuid, options[index]);
        } else {
          Bot.im(ownerName, "Invalid option received. Please choose one of the following options:\n\n" + options.join("\n") + "\nIgnore - Ignores the dialog\n\n(The options are CaSe SeNsItIvE)");
        }
      }
    }
  }
});
```