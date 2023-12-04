# Setup
Install basic packages
`opam install -y utop odoc ounit2 qcheck bisect_ppx menhir ocaml-lsp-server ocamlformat ocamlformat-rpc`
# Basics
## Overview
- functional programming language
	- abstraction = mathematical function
	- for the same input, it always produces the same output
	- stateless
	- immutability
		- no side-effects
		- variables never change value
- functions are first-class
-  `O` stands for "objective"
- ML = meta language

## Features
- _statically-typed_
- _type-safe_
- pattern matching
- type inference
- polymorphism
- GC
- modules

## Top level
- REPL: `utop`
### Syntax
- double semicolon
- reading from right to left
- let definitions
	- `let x = e`
	- x = identifier
		- have to start with lowercase letters
	- 1. evaluate e
	- 2. bind the value to x
- Top level directives start with `#`
	- Module include
### Types
- string enclosed in `""`
- string concatenation is `^`
- two sets of math operators, one for int, one for float
- type annotation: `(exp : type)`

### Functions
- can be called with parenthesis or not
- applied
- 

# References