# Logging

There are two types of logs in the Bot Playground:

* **Error log**
* **Runtime log**

# Log Differences

| **Error Log** | **Runtime Log** |
|----|----|
| Entries are added on errors, or by using `_assert()`, `console.warn()` or `console.error()`. | Entries are added using `console.log()`. |