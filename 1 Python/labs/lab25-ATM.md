
# Lab 25: ATM

Let's represent an ATM with a class containing a balance property. A newly created account will default to a balance of 0. Implement the initializer, as well as the following methods:

- `check_balance(self)` returns the account balance
- `deposit(self, amount)` deposits the given amount in the account
- `check_withdrawal(self, amount)` returns true if the withdrawn amount won't put the account in the negative
- `withdraw(self, amount)` withdraws the amount from the account and returns it

## Version 2

Have the ATM maintain a list of transactions. Every time the user makes a deposit or withdrawal, add a string to a list saying 'user deposited $15' or 'user withdrew $15'. Add a new function `print_transactions()` to your class for printing out the list of transactions.

## Version 3

Allow the user to enter commands into a REPL.
```
> what would you like to do (deposit, withdraw, check balance, history)?
> deposit
> how much would you like to deposit?
> $5
> what would you like to do (deposit, withdraw, check balance, history)?
> check balance
> balance: $5
```
