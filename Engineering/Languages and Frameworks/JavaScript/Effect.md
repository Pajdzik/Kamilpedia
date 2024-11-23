# Notes
- possible to import with a namespace e.g. `import * as Effect from "effect/Effect"`
	- worse for tree shaking
- it prefers functions over methods
	- better for tree shaking
	- methods are attached to objects or prototypes
- `Effect` type
	- immutable description of an operation
	- lazy
		- when instantiated it does not execute immediately
	- `Effect<Success, Error, Requirements>`
		- Requirements represent dependencies
		- an equivalent of `(r: Context<Requirements>) => Success | Error`
	- 
# References
- [Getting Started](https://effect.website/docs/getting-started)