# Scan nearby avatars

This example script scans for nearby avatars and logs their details.\nBecause `console.log` is limited to **4 KB**, the script logs each avatar individually to avoid truncation.

```javascript
// Bots Playground script: [TEST] nearbyAvatars (build 1 by Glaznah Gassner)
console.log(`${process.name} started`);

const result = await Bot.scanNearbyAvatars();
console.log(`Avatars arrived: (${JSON.stringify(result).length} bytes)`);

if (JSON.stringify(result).length < 1024) {
  console.log("Raw response:", result);
}

if (!result.success) {
  console.log("Error scanning avatars: " + result.error);
}

if (!result.avatars) {
  console.log("No avatars found in command result");
} else {
  for (const avatar of result.avatars) {
    // Uncomment below for full raw output
    // console.log(JSON.stringify(avatar, null, 2)); 

    console.log(`${avatar.name}: seen for ${avatar.seenSeconds} seconds`);
  }
}

process.exit();
```

# Comments

* Uses `Bot.scanNearbyAvatars()` to detect avatars within range.
* Logs total response size and outputs details for each detected avatar.
* Avoids exceeding `console.log`'s **4 KB** output limit by logging entries individually.
* Gracefully exits once all avatars have been processed.