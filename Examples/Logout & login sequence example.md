# Logout & login sequence example

This example demonstrates how to log the bot out, wait for 30 seconds, and then log back in.\nIt also sets up event handlers to track the login/logout process.

```javascript
Bot
  .on("before_logout", function(event) {
    console.log("Event: Bot is logging out");
  })
  .on("before_login", function(event) {
    console.log("Event: Bot is logging in");
  })
  .on("after_login", function(event) {
    console.log("Event: Bot has logged in");
  });

// Logout bot after a few seconds
// (otherwise bot may not detect the events we just set)
setTimeout(function() {
  console.log("Logging out the bot...");
  Bot.logout();
}, 5 * 1000);

// Then wait 30 seconds and log back in
setTimeout(function() {
  console.log("Starting log in sequence...");
  Bot.login();
}, 30 * 1000);
```

# Comments

* Demonstrates how to handle bot login/logout lifecycle events:
  * `before_logout` — triggered just before the bot logs out.
  * `before_login` — triggered before logging in.
  * `after_login` — triggered when the login completes successfully.
* Shows that multiple `Bot.on()` calls can be chained together for cleaner event registration.
* Uses `setTimeout()` to schedule logout and login operations with delays.