# touchPrim

Touches an in-world object (prim) by its UUID.

```javascript
Bot.touchPrim(uuid);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `uuid` | yes | The UUID of the object to touch. |

## Output

This function does not return anything.

## Comments

It is important to remember that the bot can only touch objects it has already "seen":

* After logging in, give the bot about 30 seconds to load surrounding objects.
* The same applies after teleporting.
* Nearby objects load faster than distant ones.
* If you want the bot to touch a distant object (for example, on the other side of the region), visit it first so the bot can "see and remember" it.

## Examples

Touch a special test object in SmartBots office (the object is located at **DuoLife/210/151/31**):

```javascript
// SmartBots Playground code start v1.0 (automatic line)
Bot.on("chat_message", function(event) {
  console.log("Got a message: " + event.message);

  // Teleport home. Please don't leave your bots at DuoLife!
  Bot.teleport("HOME");
});

// Go to testing object

Bot.teleport("DuoLife/211/152/31");

console.log("Teleported, touching object in 3 seconds...");

setTimeout(function() {
  Bot.touchPrim("a6b4be6c-ca10-398f-846e-ea933cebfda2");
  console.log("Object touched, waiting for object's message...");
}, 3000);
```

The test object's LSL code:

```csharp
default {
    touch_start(integer total_number) {
        llOwnerSay("touched by " + llDetectedName(0));
        llRegionSayTo(llDetectedKey(0), 0, "I'm touched by " + llDetectedName(0));
    }
}
```