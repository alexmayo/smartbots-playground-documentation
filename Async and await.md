# Async and await

# TL;DR

This is what an `async/await` Playground script looks like:

```javascript
const AVATAR = "Smartbots Resident";

console.log("The age is:", await getAge(AVATAR));

async function getAge(slname) {
  const res1 = await Bot.name2key(slname);
  const res2 = await Bot.avatarProfile(res1.slkey);
  return res2.age;
}

console.log("This log appears only after all calculations are complete");
```

# A Long Story

`async/await` is JavaScript's modern approach to asynchronous programming.\nThe concept may seem confusing at first, but once you get used to it, you'll find `async` functions extremely powerful and readable.

Let's start with an example from the **Callbacks and return values** page:

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

After rewriting it using `await`, the code looks much simpler:

```javascript

const slname = "Smartbots Resident";

const res1 = await Bot.name2key(slname);
// this code will be called when name2key() gets completed

console.log("Got the UUID!", res1.slkey);

const res2 = await Bot.avatarProfile(res1.slkey);
// this code will be called when avatarProfile() gets completed

console.log("Got the age!", res2.age);

await Bot.im("Glaznah Gassner", `The age of ${slname} is ${res2.age}`);

console.log("The script has been completed");
```

Looks much simpler and easier!

# Notes

Remember that `await` may appear **only inside** `**async**` **functions**.\nIf you need to use `await`, wrap your logic inside an `async` function:

```javascript
const AVATAR = "Smartbots Resident";

console.log("The age is:", await getAge(AVATAR));

async function getAge(slname) {
  const res1 = await Bot.name2key(slname);
  const res2 = await Bot.avatarProfile(res1.slkey);
  return res2.age;
}
```

# More Examples

Check **[Examples](./Examples.md)** for more code samples to experiment with.