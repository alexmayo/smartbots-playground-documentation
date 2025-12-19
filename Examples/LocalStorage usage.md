# LocalStorage usage

This script demonstrates the basic usage of `localStorage.set()` and `localStorage.get()` functions.

```javascript

var CONFIG = {};

restoreConfig();

CONFIG.runs++;
console.log("This script is starting for " + CONFIG.runs + " time");

saveConfig();

function restoreConfig() {
  var cnf = localStorage.get("my_config");
  CONFIG = { runs: 0 };
  
  if (typeof(cnf) != "undefined" && cnf != "") {
    CONFIG = JSON.parse(cnf);
  }
}

function saveConfig() {
  localStorage.set("my_config", JSON.stringify(CONFIG));
}
```