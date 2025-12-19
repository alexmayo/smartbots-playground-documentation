# http.get

Retrieves data from an HTTP source.

```javascript
http.get(url, query)
    .then(function(response) {
        ...
    });

// or with await:
var response = await http.get(url, query);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `url` | yes | The URL to retrieve. |
| `query` | optional | *(object)* Optional URL query string parameters. Can be appended to the URL or passed as an object. |

# Output

This function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | boolean | True if the command completed successfully. |
| `error` | string | Error message if the command failed. |
| `statusCode` | number | *(On success)* The HTTP status code. |
| `headers` | array | *(On success)* Array containing the HTTP headers. |
| `body` | string | *(On success)* The body of the reply as a string. |

# Comments

This function performs an HTTP **GET** request to the specified URL.\nQuery parameters can be either:

* appended directly to the URL, e.g. `example.com/?param1=1&param2=2`, or
* passed as an object, e.g. `{ param1: 1, param2: 2 }`

# Limitations

The response body length is limited to **4096 bytes**.

# Examples

```javascript
console.log("Doing http request...");

http.get("https://mysmartbots.com")
    .then(function(response) {
        console.log("http result:", response.body);
    })
    .then(function() {
        // Gracefully stop the test script
        exit();
    });
```

A more advanced example with error handling:

```javascript
console.log("Doing http request...");

http.get("https://mysmartbots.com")
    .then(function(result) {
        if (!result.success) {
            // On error display the error message and stop the processing
            console.log("HTTP error:", result.error);
            throw "";
        }

        console.log("http result:", result.body);
    })
    .catch(function(err) {
        // This block allows cancelling the processing chain with throw ""
        if (err != "") { throw err; }
    })
    .then(function() {
        // Gracefully stop the test script
        exit();
    });
```