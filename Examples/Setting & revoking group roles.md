# Setting & revoking group roles

This example demonstrates how to **assign** or **revoke** group roles using the `Bot.setGroupRole()` and `Bot.revokeGroupRole()` functions.

```javascript
var operation = "SET"; // SET or REVOKE

var AVATAR = "042536ca-dc19-45ef-bd3c-2f3c829d4e56";
var GROUP = "6c9ecdd2-dcd8-384d-00bc-57a5dc3e7396";
var ROLE = "ff37ff6a-595f-eff4-6ae2-6a5ec9ade464";

var promise;

console.log("The goal is to " + operation + " the group role");

switch(operation) {
  case "SET":
    promise = Bot.setGroupRole(AVATAR, GROUP, ROLE);
    break;

  case "REVOKE":
    promise = Bot.revokeGroupRole(AVATAR, GROUP, ROLE);
    break;
}

promise.then(function(result) {
  console.log("Command result: " + JSON.stringify(result));
});

// Gracefully exit after a short delay

setTimeout(function() {
  exit();
}, 1000);
```

# Comments

* Use `"SET"` to assign the specified role to the avatar.
* Use `"REVOKE"` to remove the role from the avatar.
* The script logs the command result as JSON for easy inspection.

This is useful for managing group memberships programmatically within the Bot Playground.