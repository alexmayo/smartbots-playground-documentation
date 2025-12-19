# Random group tag activator

This example demonstrates how to retrieve the list of groups the bot is a member of using `Bot.listGroups()`,\nthen activate the first group tag using `Bot.activateGroup()`.

```javascript
Bot.listGroups()
.then(function(result) {
  // We don't use Object.keys() below because it was not
  // supported in early versions of Bots Playground
  var cnt = 0;
  var uuid = "";

  for (k in result.groups) {
    cnt++;

    // Activate the very first group in list
    if (uuid == "") { uuid = k; }
  }
  
  console.log("Got groups. I'm a member of " + cnt + " group(s)" + "\n" +
              "I will activate this group tag: " + result.groups[uuid]);
  
  // We use Promise here. See Bot Playground docs
  return Bot.activateGroup(uuid);
})
.then(function(result) {
  console.log("group activated successfully: " + result.success);
  exit();
});
```

# Comments

* Uses `Bot.listGroups()` to retrieve all groups the bot is a member of.
* Selects the first group from the list (no randomization implemented in this version).
* Calls `Bot.activateGroup(uuid)` to activate that group tag.
* Logs the group information and success status.
* Exits once the operation completes successfully.