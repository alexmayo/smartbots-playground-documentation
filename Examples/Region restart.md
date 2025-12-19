# Region restart

This example demonstrates how to work with region restarts using Bot Playground commands and events.

**The script performs the following actions:**


1. Initiates a region restart.
2. Waits for 10 seconds.
3. Cancels the restart.
4. Logs all related restart events.

```javascript
console.log(`${process.name} started`);

Bot.on("region_restart", (event) => {
  console.log(`region_restart:`, event);
});

Bot.on("region_restart_cancelled", (event) => {
  console.log(`region_restart_cancelled:`, event);
});

Bot.regionRestart(240);
console.log("Region restart requested");

await sleep(10 * 1000);

Bot.regionRestartCancel();
console.log("Region restart cancelled");
```

# Comments

* `Bot.regionRestart(seconds)` schedules a region restart after the given number of seconds.
* `Bot.regionRestartCancel()` cancels a previously scheduled restart.
* Events `region_restart` and `region_restart_cancelled` are emitted and can be used to monitor restart progress.
* The example uses `await sleep(10 * 1000)` to pause execution for 10 seconds between actions.