# Built-in Functions

The basic built-in functions do not relate to bot functionality. Instead, they allow writing flexible scripts.

```javascript
setTimeout(function() {
  console.log("Timer has fired!");
}, 3000); 
```

# List of functions

| **Script Details** |
|----|
| `[process.name](./Built-in%20Functions/process.name.md)` | Read-only property reflecting running script name. |
| `[process.release](./Built-in%20Functions/process.release.md)` | Read-only property reflecting the script release version (for store scripts). |
| **Program Flow** |
| `[process.exit](./Built-in%20Functions/process.exit.md)` | Ends the execution of the program. |
| `[process.sleep](./Built-in%20Functions/process.sleep.md)` | Pauses a program execution. |
| [Timer control](./Built-in%20Functions/Timer%20control.md) | Standard timer control routines of JavaScript: setTimeout, setInterval etc. |
| **Persistent Bot Storage** |
| `[localStorage.get](./Built-in%20Functions/localStorage.get.md)` | Restores a string value from a persistent storage. |
| `[localStorage.set](./Built-in%20Functions/localStorage.set.md)` | Puts a string value into a persistent storage. |
| `[localStorage.keys](./Built-in%20Functions/localStorage.keys.md)` | Returns the list of the available keys in a persistent storage. |
| `[localStorage.on](./Built-in%20Functions/localStorage.on.md)` | Adds the event callback on localStorage. |
| **User Settings** |
| `[userSettings.\*](./Built-in%20Functions/userSettings.*.md)` | Allows accessing the settings specified by the script user. |
| **HTTP** |
| `[http.get](./Built-in%20Functions/http.get.md)` | Retrieves data from a HTTP source. |
| `[http.post](./Built-in%20Functions/http.post.md)` | Retrieves data from a HTTP source using the POST method. |
| `[http.requestWebhookUrl](./Built-in%20Functions/http.requestWebhookUrl.md)` | Allocates a new, per-run webhook URL and token for the current script instance. |
| **Debug** |
| `[console.log](./Built-in%20Functions/console.log.md)` | Logs data to the runtime log. |
| `[console.warn](./Built-in%20Functions/console.warn.md)` | Logs data to the error log. |
| `[console.error](./Built-in%20Functions/console.error.md)` | Logs data to the error log. |
| `[_assert](./Built-in%20Functions/_assert.md)` | Logs data to the error log if the assertion is false. |