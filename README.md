# banking_system_in_python_using_formal_method_z3
This project is a Python-based Banking System that simulates the basic operations of a bank. It incorporates both functional programming for handling bank operations and formal verification using the Z3 solver to ensure system correctness. Below is a detailed breakdown of the project:

# 1. Key Components
# 1.1 BankAccount Class
This class models an individual bank account and includes:

# Attributes:
account_id: Unique identifier for the account.

owner: Name of the account owner.

balance: Current account balance.

transactions: List to store the transaction history.
# Methods:
deposit(amount): Adds the specified amount to the balance if it's positive and logs the transaction.

withdraw(amount): Subtracts the specified amount from the balance if it doesn’t result in a negative balance.

get_balance(): Returns the current balance.

print_transactions(): Prints the transaction history.
# 1.2 Bank Class
This class manages multiple accounts in the banking system and includes:

# Attributes:
accounts: A dictionary storing all bank accounts, keyed by their account_id.
# Methods:
create_account(account_id, owner, initial_balance): Creates a new account with the provided details.

get_account(account_id): Retrieves an account by its ID.

print_all_accounts(): Prints details of all accounts in the bank.
# 1.3 Formal Verification Using Z3
The project uses the Z3 Solver to ensure the correctness of account operations, specifically focusing on preventing negative balances.

# Steps:
# Symbolic variables balance and withdrawal are created using Z3.
Constraints are added:

balance >= 0: Ensures the balance is never negative.

withdrawal > 0: Ensures withdrawals are positive.

balance - withdrawal >= 0: Prevents overdrawing the account.

The Z3 solver checks these constraints and reports whether the system is safe or unsafe.
# 2. Interactive Banking System
The run_banking_system function provides an interactive interface for users to perform operations.

# Menu Options:
Create Account:

Inputs: Account ID, owner's name, initial balance.

Adds the new account to the system.

Deposit Money:

Inputs: Account ID, deposit amount.

Adds the amount to the specified account's balance.

Withdraw Money:

Inputs: Account ID, withdrawal amount.

Subtracts the amount if it doesn’t cause a negative balance.

Check Balance:

Inputs: Account ID.

Displays the current balance of the specified account.

Show Transaction History:

Inputs: Account ID.

Displays the transaction history for the specified account.

Show All Accounts:

Displays details of all accounts in the bank.

Verify Account Balance Safety:

Inputs: Account ID.

Uses Z3 to verify the account's balance safety.

Exit:

Exits the system.
# 3. Features
User-Friendly Interface: Allows users to create accounts, deposit/withdraw money, and view balances and transactions interactively.

Transaction History: Logs every deposit and withdrawal for each account.

Formal Verification: Ensures that withdrawals don’t result in negative balances using the Z3 theorem prover.
# 4. Workflow
User Input:

The user selects an operation from the menu and provides the required inputs.

Account Management:

The system interacts with the Bank and BankAccount classes to perform the requested operation.

Validation:

Each operation includes validation checks (e.g., positive amounts, sufficient funds).

Verification:

The Z3 solver verifies critical constraints like non-negative balances.

Output:

The system provides feedback, such as updated balances or verification results.
# 5. Why Use Z3 for Verification?
The Z3 solver ensures the system’s safety by verifying constraints symbolically, rather than relying solely on runtime checks. This approach:


Detects potential errors (e.g., negative balances) during development.

Provides mathematical proof of correctness for critical operations.
# 6. How to Run the Project
Install Z3:

Copy code

!pip install z3-solve

Run the Code:

Execute the script in a Python environment (e.g., Google Colab or local Python IDE).

Use the interactive menu to test the system.
# 7. Advantages
Robust Design: Validates inputs and operations.

Formal Verification: Guarantees safety against negative balances.

Extensible: Can be expanded with additional features (e.g., loans, interest calculation).
