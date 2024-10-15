# Chapter 1
## 1.1 Why a Database System?
- **database** – a collection of data stored on a computer
	- typically organized into *records*
- **database systems** – helps in records management
- features of a database:
	- persistent – *note: does it disqualify Redis etc?*
	- shared
	- accurate
	- can be very large
	- must be usable
### 1.1.1 Record Storage
- naive solution is to save data in files
	- will become slower with the size
		- for both reads and writes
### 1.1.2 Multi-user Access
- incorrectly implemented concurrency can cause data to be incorrect
- database should have conflict prevention system
- data can be committed
### 1.1.3 Dealing with Catastrophe
- needs to provide graceful recovery
### 1.1.4 Memory Management
- RAM is faster than flash memory which is faster than hard drives
	-  RAM is about 1000 times faster than flash and 100,000 times faster than disk
### 1.1.5 Usability
- data needs to be extractable
- standard query language for relational databases is SQL
## 1.2 The Derby Database System
- `ij` – command line tool for the Darby database
## 1.3 Database Engines
- ij consists of two parts
	- user interface
	- database engine
## 1.4 The SimpleDB Database System
- SimpleDB database system - small, easily
readable, and easily modifiable
- SimpleIJ – simplified version of `ij`
- 