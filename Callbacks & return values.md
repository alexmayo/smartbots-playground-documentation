# Callbacks & return values

JavaScript — and Playground — are mostly **asynchronous**.\nThis means that when you call an operation, it starts in the background immediately, and your program continues running without waiting for the result.

This can cause trouble if you depend on that result. For example, imagine you want to:


1. Get an avatar's UUID
2. Use that UUID to find the avatar's age
3. Finally, send the age to another avatar


:::info
**Important update:**\nAs of **October 2020**, Bot Playground commands support the `await` instruction.\nIt's recommended for most cases, as it makes scripting much easier!\nSee [Async and await](./Async%20and%20await.md) for examples.

:::

# Starting from Scratch

To start, use the `name2key` bot command:

```javascript
Bot.name2key("Glaznah Gassner");
```

Okay, we know how to ask the question. But how do we get the reply?

# Way 1: Using Callbacks

The simplest way is to use **callback functions**:

```javascript
var slname = "Smartbots Resident";

Bot.name2key(slname, function(result) {
  console.log("Got the UUID!", result.slkey);

  // Oh, now the next step, also with a callback
  Bot.avatarProfile(result.slkey, function(result2) {
    console.log("Got the age!", result2.age);

    Bot.im("Glaznah Gassner", "The age of " + slname + " is " + result2.age);
  });
});

console.log("I've asked for UUID and now waiting for answer");
```

Looks a bit weird, right?\nImagine adding a third callback level — this is called **callback hell**.

# Way 2: Promises

To avoid callback hell, Bot Playground supports the **Promise** object.\nHere's how it works:

```javascript
var slname = "Smartbots Resident";

Bot.name2key(slname)
  .then(function(result) {
    // this code will be called when name2key() gets completed
    console.log("Got the UUID!", result.slkey);

    // Oh, now the next step
    return Bot.avatarProfile(result.slkey);
  })
  .then(function(result2) {
    // this code will be called when avatarProfile() gets completed
    console.log("Got the age!", result2.age);

    Bot.im("Glaznah Gassner", "The age of " + slname + " is " + result2.age);
  });

console.log("I've asked for UUID and now waiting for answer");
```

Much easier, right?\nEach command (`name2key`, `avatarProfile`, etc.) returns a **Promise** object.\nYou can call its `.then()` function to set your handler — it runs once the command completes.

Subsequent commands can be **chained** as shown above.\nNote the `return Bot.avatarProfile()` — this ensures the next `.then()` is chained to it.

# Breaking the Promise Function Chain

What if you need to **break the chain** — for example, when a recipient UUID cannot be found?

```javascript
var slname = "Smartbots Resident";
var all_money = 0;
var uuid = "";

// we want to send money to avatar

Bot.name2key(slname)
  .then(function(result) {
    // Oh-oh, a name mistake!
    if (!result.success) { throw "Unknown recipient!"; }

    // we know the recipient's UUID now
    uuid = result.slkey;
    return Bot.getBalance();
  })
  .then(function(result) {
    // we know our balance now
    all_money = result.balance;
    Bot.giveMoney(uuid, all_money);
  })
  .catch(function(error) {
    // this code will be called when something wrong happened with a command
    console.log("We've faced an error: " + error);
  })
  .then(function() {
    // Stop our script at any case
    console.log("Script has been finished");
    exit();
  });
```

We added two important parts:

```javascript
if (!result.success) { throw "Unknown recipient!"; }
```

and

```javascript
.catch(function(error) {
  console.log("We've faced an error: " + error);
});
```

Throwing an error cancels all further operations until the `.catch()` block.\nIf everything succeeds, `.catch()` is skipped.

The `.then()` block after `.catch()` runs **regardless**,\nmaking it perfect for cleanup or stopping your script.

# More Examples

Check [Examples](./Examples.md) for more scripts to experiment with.