# localStorage.set

Stores a string value in persistent storage. Also see `localStorage.get()`.

```javascript
localStorage.set(name, value);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `name` | yes | The name of the persistent value you want to store. |
| `value` | yes | The string value you want to save. |

# Output

This function does not return anything.

# Limitations

`localStorage` is intended for short key-value pairs.\nThe maximum size of a stored value is **6144 bytes**.\nIf you exceed this limit, the script generates a warning:

```
localStorage value is more than 6144 bytes and not persistent
```

If you need to store large amounts of data (such as multiple keys with several kilobytes each),\nconsider using your own key-value database via HTTP requests.

# Comments

This function works similarly to the browser's `localStorage.set()` method.\nIt saves a value to persistent storage shared among all scripts of the same bot.

You can set values in one script and retrieve them from another using `localStorage.get()`.

Only **string** values are supported.\nTo store more complex data, use `JSON.stringify()`:

```javascript
localStorage.set("userData", JSON.stringify({ name: "Alex", age: 30 }));
```

# Inter-script Communication

Calling `localStorage.set()` will trigger the `localStorage.on("update")` event\nin other scripts of the same bot (but not in the current one).