# http.post

Retrieves data from an HTTP source using the **POST** method.

```javascript
await http.post(url, queryData, "json", requestOptions);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `url` | yes | The URL to send the POST request to. |
| `queryData` | optional | *(object)* Optional POST parameters. |
| `contentType` | optional | *(string)* The content type of the request. See **Content Type** below for details. |
| `requestOptions` | optional | *(object)* Additional request options such as custom headers. See **Request HTTP Headers** below. |

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

This function performs an HTTP **POST** request to the specified URL.\nThe request body can be sent as a `queryData` object:

```javascript
var response = await http.post("https://ptsv2.com/t/h6rf5-1631886515/post", {
  param1: 1,
  param2: 2
});
```

You can use <https://ptsv2.com> to test your POST requests.

# Content Type

By default, the request is sent as `application/x-www-form-urlencoded`\n(i.e., key=value pairs joined by `&`).

```javascript
http.post(url, queryString);
// or equivalently

http.post(url, queryString, "form");
```

To send JSON instead, specify `"json"` as the `contentType` argument — this sets\nthe content type to `application/json` and automatically encodes the data:

```javascript
http.post(url, queryData, "json");
```

# Request HTTP Headers

You can set HTTP headers using the `requestOptions` object.\nCurrently, headers are the only supported option.

```javascript
var response = await http.post(
  "https://ptsv2.com/t/h6rf5-1631886515/post",
  { param1: 1, param2: 2 },
  "json",
  {
    "headers": {
       "x-my-header-1": "value-1",
       // ...
    }
  }
);
```

# Limitations

The response body length is limited to **4096 bytes**.

# Examples

A simple POST request using `await`:

```javascript
console.log("Doing http request...");

var response = await http.post("https://ptsv2.com/t/h6rf5-1631886515/post", { param1: 1, param2: 2 });
console.log("http result:", response.body);

// Gracefully stop the test script

exit();
```

A more complex example with error handling (using Promises):

```javascript
console.log("Doing http request...");

http.post("https://ptsv2.com/t/h6rf5-1631886515/post", { param1: 1, param2: 2 })
  .then(function(result) {
    if (!result.success) {
      // On error, display the error message and stop the processing
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