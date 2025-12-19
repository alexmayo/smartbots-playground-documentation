# process.sleep

Pauses program execution for a specified amount of time.

```javascript
await process.sleep(timeMs);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `timeMs` | yes | Sleep time in milliseconds. |

# Output

This function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | boolean | True if the command completed successfully. |
| `error` | string | Error message if the command failed. |

# Comments

This function delays code execution for a specified duration.\nIt is **asynchronous**, so it must be used with `await` or `.then()` — you cannot simply write:

```javascript
doSomething();
process.sleep(1000);
doAfterDelay(); // ❌ This won't wait
```

Instead, use `async/await` or a promise chain (see examples below).

The `process.sleep()` function immediately returns a Promise.\nUse `await` to pause script execution properly.


:::info
**Note:** Previously known as the bare function `sleep()`.

:::

# Examples

**1. Using async/await (recommended):**

```javascript
console.log("one1");
await process.sleep(2000);
console.log("two2");
```

**2. Standalone usage:**

```javascript
console.log("one1");
process.sleep(2000)
  .then(function() {
    console.log("two2");
  });
```

**3. Within a Promise chain:**

```javascript
http.get("https://mysmartbots.com")
  .then(function() {
    console.log("one");
    return process.sleep(2000);
  })
  .then(function() {
    console.log("two");
  })
  .then(function() {
    // Gracefully stop the test script
    exit();
  });
```