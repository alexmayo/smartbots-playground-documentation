# Working with L$

The following script demonstrates how to send a specified amount of money (`AMOUNT_TO_SEND`) to a recipient (`RECIPIENT`).

**The script performs the following steps:**


1. Calls `name2key()` to get the recipient's UUID.
2. Checks the bot's available balance using `getBalance()`.
3. Sends money using `giveMoney()`.
4. Verifies the transaction and compares the new balance.

```javascript
var RECIPIENT = "Glaznah Gassner";
var AMOUNT_TO_SEND = 1;

var uuid = "";
var balance;

Bot
  // 1. First, request the UUID of the recipient
  .name2key(RECIPIENT)

  // 2. Save UUID, then check our balance
  .then(function(result) {
    uuid = result.slkey;
    if (!result.success) { 
      throw "Can't resolve recipient UUID"; 
    } else {
      console.log("The recipient's UUID is " + uuid);
    }	

    return Bot.getBalance();
  })

  // 3. Save balance (for a future check) and send money
  .then(function(result) {
    balance = result.balance;
    console.log("My balance is " + balance);
  
    if (balance < AMOUNT_TO_SEND) { 
      throw "I have not enough money to deliver"; 
    }
  
    return Bot.giveMoney(uuid, AMOUNT_TO_SEND, "Playground test");
  })

  // 4. Check the operation result and check our balance again
  .then(function(result) {
    console.log("giveMoney successful: " + (result.success ? "yes" : "no"));
  
    return Bot.getBalance();
  })

  // 5. Compare with expected balance
  .then(function(result) {
    console.log("New balance: " + result.balance + "\n" +
                "expected balance: " + (balance - AMOUNT_TO_SEND));
  })

  // 6. Handle any errors that occur
  .catch(function(error) {
    console.log("Script error: " + error);
  })

  // 7. Exit — stop the script after completion
  .then(function() {
    exit();
  });
```