# Account Class and Banking Account Manager

This repository contains a suite of scripts and classes to manage financial accounts, including savings accounts and certificates of deposit (CDs). It demonstrates how to calculate interest earned and update account balances using the `Account` class.

---

## Account Class

The `Account` class provides functionality for managing basic account operations, such as setting balance and interest.

### Class Description

The `Account` class allows for:
- Initializing an account with a balance and interest rate.
- Updating the balance and interest via dedicated methods.

### Attributes
1. **`balance`**: Represents the current balance of the account.
2. **`interest`**: Represents the interest rate or amount associated with the account.

### Methods
- **`__init__(self, balance, interest)`**  
  Initializes an account object with the given `balance` and `interest`.

- **`set_balance(self, balance)`**  
  Updates the `balance` of the account.  
  **Docstring**: `"Sets the balance for the account."`

- **`set_interest(self, interest)`**  
  Updates the `interest` of the account.  
  **Docstring**: `"Sets the interest gained for the account."`

### Example Usage
```python
from account import Account

# Create an Account instance
my_account = Account(balance=1000, interest=0.05)

# Set new balance
my_account.set_balance(1500)

# Set new interest
my_account.set_interest(0.04)

# Access account attributes
print(f"Balance: {my_account.balance}")
print(f"Interest: {my_account.interest}")


from cd_account import create_cd_account

# Example parameters
initial_balance = 1000.00
annual_interest_rate = 5.0  # 5% APR
term_in_months = 12

updated_balance, interest_earned = create_cd_account(
    initial_balance, annual_interest_rate, term_in_months
)

print(f"Updated Balance: ${updated_balance:.2f}")
print(f"Interest Earned: ${interest_earned:.2f}")

from savings_account import create_savings_account

# Example parameters
initial_balance = 2000.00
annual_interest_rate = 3.0  # 3% APR
term_in_months = 6

updated_balance, interest_earned = create_savings_account(
    initial_balance, annual_interest_rate, term_in_months
)

print(f"Updated Balance: ${updated_balance:.2f}")
print(f"Interest Earned: ${interest_earned:.2f}")

from savings_account import create_savings_account
from cd_account import create_cd_account

def main():
    # Prompt user for savings account details
    savings_balance = float(input("Enter the initial balance for the savings account: "))
    savings_interest = float(input("Enter the interest rate (in %) for the savings account: "))
    savings_maturity = int(input("Enter the number of months for the savings account: "))

    # Calculate savings account details
    updated_savings_balance, interest_earned = create_savings_account(
        savings_balance, savings_interest, savings_maturity
    )
    print(f"Savings Account Updated Balance: ${updated_savings_balance:.2f}")
    print(f"Interest Earned: ${interest_earned:.2f}")

    # Prompt user for CD account details
    cd_balance = float(input("Enter the initial balance for the CD account: "))
    cd_interest = float(input("Enter the interest rate (in %) for the CD account: "))
    cd_maturity = int(input("Enter the number of months for the CD account: "))

    # Calculate CD account details
    updated_cd_balance, interest_earned = create_cd_account(
        cd_balance, cd_interest, cd_maturity
    )
    print(f"CD Account Updated Balance: ${updated_cd_balance:.2f}")
    print(f"Interest Earned: ${interest_earned:.2f}")

if __name__ == "__main__":
    main()






