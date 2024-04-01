# Double-entry accounting
## Terms
- **account** – accumulator (~bag/container)
	- starts empty
	- **balance** – number of units in the bag at the particular moment in time
		- can be negative
	- **posting** – changing the state of the account
	- types:
		- **balance** – 
		- **delta** – 
- **debit**
	- in asset accounts "removed from your account"
		- withdrawal
- **credit**
	- in asset accounts "deposited in your account"
		- deposit

## Statements
### Timeline
```mermaid
timeline
	title account balance
	start: 0
	...: 1000
	+100: 1100
	-25: 1075
	-200: 875
	
```

### Table
* balance is always including the transaction from the same row (_after_ the transaction)
#### Single amount column

| Date              | Description | Amount  | Balance |
| ----------------- | ----------- | ------- | ------- |
| 2023/01/01        | [...]       | 100.00  | 1100.00 |
| 2023/01/02        | [...]       | -25.00  | 1075.00 |
| 2023/01/03        | [...]       | -200.00 | 875.00  |
| **Final balance** |             |         | 875.00  |
#### Split column
| Date              | Description | Debit  | Credit | Balance |
| ----------------- | ----------- | ------ | ------ | ------- |
| 2023/01/01        | [...]       |        | 100.00 | 1100.00 |
| 2023/01/02        | [...]       | 25.00  |        | 1075.00 |
| 2023/01/03        | [...]       | 200.00 |        | 875.00  |
| **Final balance** |             |        |        | 875.00  |

# Sources
