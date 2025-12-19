# localStorage.on

Adds an event callback for changes in `localStorage`. Also see `localStorage.set()`.

```javascript
localStorage.on(eventName, callback);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `eventName` | yes | The name of the event. Currently, only the `"update"` event is supported. |
| `callback` | yes | The callback function to trigger when the event occurs. It has the signature function(entry, value, script)where:<br>•entry— the key name that was updated<br>•value— the new value<br>•script — the name of the script that made the change |

# Output

This function does not return anything.

# Limitations

See `localStorage.set()` for storage limitations.

# Comments

Use this function to detect when other scripts perform a `localStorage.set()` operation.


:::info
The `"update"` event does **not** trigger for `localStorage.set()` calls made within the **same script**.

:::

# Examples

To see how `localStorage.on("update")` works, you'll need two scripts:

**Listener Script:**

```javascript

localStorage.on("update", function(entry, value, script) {
  console.log("localStorage got updated:", entry, "=", value, "by script", script);
  exit();
});
```

**Initiator Script:**

```javascript

localStorage.set("data", "data from 1");
exit();
```

**How to Run:**


1. Launch the **Listener** script (it will keep running).
2. Launch the **Initiator** script (it will run and stop).
3. Switch back to the **Listener** script and check its runtime logs — it should show the update event.