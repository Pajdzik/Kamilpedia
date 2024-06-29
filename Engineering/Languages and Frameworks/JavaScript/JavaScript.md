# Concepts
## Modules
### Barrel files
- Barrel files are files that only export other files and contain no code themselves.
- a pattern where every folder got its own `index.js` re-exporting code from the directory
- *Problem*: a module very likely imports another barrel file which pulls in a bunch of other files, which then imports yet another barrel file and so on
### References
[Speeding up the JavaScript ecosystem - The barrel file debacle](https://marvinh.dev/blog/speeding-up-javascript-ecosystem-part-7/)

## Proxy
The `Proxy` object lets you detect when someone interacts with a property off an array or object, and run code in response.

```javascript
// An object with a nested array
let wizard = {
	name: 'Merlin',
	tool: 'wand',
	spells: ['Abbracadabra', 'Disappear']
};

// A handler object
let handler = {
	get (obj, key) {
		console.log('get', key);
		return obj[key];
	},
	set (obj, key, value) {
		console.log('set', key);
		obj[key] = value;
		return true;
	}
};

// Create a new Proxy
let wizardProxy = new Proxy(wizard, handler);
```

How to check if an object is already a proxy?

```javascript
function handler () {
	return {
		get (obj, key) {

			// If the key is "_isProxy", return true
			// This will only happen if the property is already a Proxy
			if (key === '_isProxy') return true;

			// ...

		},
		// ...
	};
}
```
### References
- [A primer on JavaScript Proxies](https://gomakethings.com/a-primer-on-javascript-proxies/)

# Front end
- [Mastering DOM manipulation with vanilla JavaScript](https://phuoc.ng/collection/html-dom/)

# References
- [Eloquent JavaScript](https://eloquentjavascript.net/)
