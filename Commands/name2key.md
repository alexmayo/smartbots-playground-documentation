# name2key

Returns the UUID of a given resident by their name.

```javascript
Bot.name2key(slname, function(result) { ... });
```

or using Promises:

```javascript
Bot.name2key(slname)
  .then(function(result) { ... });
```

## Input

| Variable | Required | Description |
|----|----|----|
| `slname` | yes | The full name of the resident — must include both first and last name, e.g. `"FirstName LastName"` or `"FirstName Resident"`. |
| `callback` |    | Optional callback function |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |
| `slkey` | string | The UUID of the avatar |

## Examples

```javascript
var AVATAR = "Glaznah Gassner";

Bot.name2key(AVATAR)
  .then(function(result) {
    console.log("The UUID using promises is " + result.slkey);
    exit();
  });

Bot.name2key(AVATAR, function(result) {
  console.log("The UUID using callback is " + result.slkey);
  exit();
});
```