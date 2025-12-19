# process.exit

Ends the execution of the program.

By default, Playground programs run indefinitely, waiting for incoming bot events, timers, and other triggers.\nYou typically don't need to stop the program explicitly. However, you may want to terminate it manually — similar to pressing **"Stop"** in the Bot Playground interface.

```javascript
process.exit();
```

# Comments

The exit procedure is **not immediate** — the script terminates after approximately **1 second**.\nHowever, all event handlers are destroyed immediately upon calling `process.exit()`,\nso no further events will be received after this point.


:::info
**Note:** Previously known as the bare function `exit()`.

:::

# Examples

```javascript
Bot.on("instant_message", function(event) {
  if (event.message == "secret string") {
    console.log("Received a secret string, program is terminating");
    process.exit();
  }
});
```