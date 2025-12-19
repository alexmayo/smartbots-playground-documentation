# localStorage.get

Restores a string value from persistent storage. Also see `localStorage.set()`.

```javascript
var data = localStorage.get("old_data");
```

# Input

| Variable | Required | Description |
|----|----|----|
| `name` | yes | The name of the persistent value you would like to retrieve. |

# Output

Returns the stored string value associated with the given name.

# Comments

This function works similarly to the browser's `localStorage.get()` method.\nIt retrieves a value from the bot's persistent storage.

The `localStorage` is shared across **all scripts** of the same bot.\nThis means you can set values in one bot script and retrieve them in another.