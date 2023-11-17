# Modules
## Barrel files
- Barrel files are files that only export other files and contain no code themselves.
- a pattern where every folder got its own `index.js` re-exporting code from the directory
- *Problem*: a module very likely imports another barrel file which pulls in a bunch of other files, which then imports yet another barrel file and so on
## References
[Speeding up the JavaScript ecosystem - The barrel file debacle](https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-7/)
