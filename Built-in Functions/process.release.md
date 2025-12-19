# process.release

Read-only property reflecting the script release version (for Store-purchased scripts).\nThe release consists of **major**, **minor**, and **patch** numbers separated by dots.

```javascript
console.log(`Script ${process.name} started, release: ${process.release}`);
```

# Example Output

```
05.00.01
```