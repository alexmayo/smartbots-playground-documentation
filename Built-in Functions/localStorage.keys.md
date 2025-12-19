# localStorage.keys

Returns the list of available keys in persistent storage. Also see `localStorage.set()`.

```javascript
localStorage.keys();
```

# Input

This function does not accept any input parameters.

# Output

Returns an array of strings containing the key names stored in persistent storage.

# Comments

Use this function to retrieve the list of keys currently stored in `localStorage`.\nUseful for iterating over stored data or debugging persistent values shared between scripts.

# Examples

```javascript
console.log("The localStorage keeps keys:", localStorage.keys());
exit();
```

Using `forEach` to iterate through all keys:

```javascript
localStorage.keys().forEach(function(key) {
  console.log(key, "=", localStorage.get(key));
});
exit();
```