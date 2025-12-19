# console.error

Logs data to the error log. Read more about error logs.

```javascript
console.error(...arguments);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `...arguments` | yes | Any number of arguments to be logged to the error log. Objects can be converted to strings using `JSON.stringify()`. |

# Output

This function does not return anything.

# Comments

Useful for reporting errors or important diagnostic information to the error log.\nAccepts multiple arguments of any type, similar to the standard JavaScript `console.error()` function.

# Examples

```javascript
console.error("An error occurred:", errorCode, errorMessage);
console.error("Object dump:", JSON.stringify(someObject));
```