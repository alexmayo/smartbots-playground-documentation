# Listing worn items

This example script loads and displays the list of items the bot is currently wearing.\nIt first locates the **"Current Outfit"** folder in the inventory, then lists its contents.

```javascript

Bot.listInventory()
.then(function(result) {
  // Find "Current Outfit" folder
  var uuid = "";
  result.list.forEach(function(itm) {
    if (itm.name == "Current Outfit") { uuid = itm.inventoryUUID; }
  });
  
  console.log("Requesting Current Outfit folder (" + uuid + ")...");
  
  // Use Promise - see Bots Playground docs for details
  return Bot.listInventory(uuid);
})
.then(function(result) {
  // Compose the list of worn items
  var worn = "";
  
  result.list.forEach(function(itm) {
    worn += itm.name + "\n";
  });
  
  console.log("I'm wearing: \n\n" + worn);
  
  exit();
});
```

# Example Output

```
13/6/2016 22:47:54

Requesting Current Outfit folder (8e4d7dfe-f2f9-b2cd-e95f-d14c903aa1e6)...

13/6/2016 22:47:56

I'm wearing: 

#Firestorm LSL Bridge v2.18

Mesh Flip Flops Red R

Avatar 111107 Eyes
#Firestorm LSL Bridge v2.18
#Firestorm LSL Bridge v2.18

Denim Shorts Mesh S
#Firestorm LSL Bridge v2.20

CATWA HAIR Bella V4 [M]
Alpha for Denim Shorts

Vikky2

New Skin (new)
Mesh Flip Flops Red L
#Firestorm LSL Bridge v2.18

erratic / cory - oversized sweater / color block 5 (M)
Vikky Dryke Blue (new)
WLM018 orange Hair

erratic / ripped stockings - thigh / brown
#Firestorm LSL Bridge v2.18
#Firestorm LSL Bridge v2.18

HV6 - Facelight
#Firestorm LSL Bridge v2.18
```

# Comments

* Uses `Bot.listInventory()` to access the inventory hierarchy.
* Locates the "Current Outfit" folder and lists the names of worn items.
* Logs the full outfit contents in a readable format.
* Demonstrates basic inventory traversal using Promises.