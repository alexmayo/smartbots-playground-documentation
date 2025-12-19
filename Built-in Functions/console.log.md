# console.log

Logs data to the runtime log. Read more about runtime logs.

```javascript
console.log(...arguments);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `...arguments` | yes | Any number of arguments to be logged to the runtime log. Objects can be converted to strings using `JSON.stringify()`. |

# Output

This function does not return anything.

# Important Notice

Since logs are saved asynchronously, consecutive `console.log()` calls may appear out of order under heavy load. For example:

```javascript
console.log("line 1");
console.log("line 2");
```

May produce the following output:

```
13/6/2016 22:25:50

line 2

13/6/2016 22:25:50

line 1
```

# Limitations

The total log data is limited to approximately **4KB–8KB** of raw string data.\nIf the output exceeds this size, the `console.log` call will be silently discarded.