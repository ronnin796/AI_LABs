# AI LAB activities
[![Ask DeepWiki](https://devin.ai/assets/askdeepwiki.png)](https://deepwiki.com/ronnin796/AI_LABs)

This repository contains a collection of Python programming exercises completed as part of AI lab activities. The solutions are implemented in a Jupyter Notebook (`.ipynb`) file.

## Lab 1: Python Fundamentals

This lab, presented in `Lab1.ipynb`, covers basic Python concepts through a series of practical exercises.

### Exercises

#### 1. User Information Collector
A simple script that prompts the user for their name, age, and city, and then prints a formatted summary.

```python
name = input("Enter your full name ")
age = input("Enter your age :")
city = input ("Enter your city:")

print(f"My name is {name } . I am {age } years old . I live in {city}")
```

#### 2. Mobile Data Bill Calculator
This exercise calculates a user's mobile data bill. It takes the total data used (in GB) and the price per GB as input. It then outputs the total bill, the average cost per MB, and a projected cost for the next month assuming a 20% increase in usage.

```python
total_data_used = float(input("Enter total data used in your mobile (GB)"))
price = float(input("Enter price per GB:"))
total_price = round((total_data_used * price) , 2)
price_per_mb = round((total_price / 1024) , 2)
next_month_usage = round((total_data_used * 1.2 ) , 2)
```

#### 3. Password Strength Checker
A function that validates a password against a set of rules:
- Minimum length of 8 characters
- Must contain at least one number
- Must contain at least one uppercase letter
- Must contain at least one special character (`%`, `@`, `&`, `#`, `!`, `^`, `*`, `(`, `_`, `-`)

It informs the user if the password is "strong" or lists the reasons why it is "weak".

```python
def check_password(password):
    errors = []
    if len(password)<8:
        errors.append("Length less than 8")
    if not has_num(password):
        errors.append("No Numbers")
    if  not has_upper(password):
        errors.append("No upper case latters")
    if not any( c in password for c in special_char):
        errors.append("No special characters")
    return errors
```

#### 4. List Flattening
This exercise demonstrates a recursive function to flatten a nested list of arbitrary depth into a single, one-dimensional list.

```python
nested_list = [ 1 , [2,3] , [4,[5,6]] , [7,8,9] ]

def flatten(nested_list):
    result = []
    for item in nested_list:
        if type(item) ==  list :
            result.extend(flatten(item))
        else:
            result.append(item)
    return result

flattened_list = flatten(nested_list)
print(flattened_list)
# Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

#### 5. Loan Eligibility Checker
A program that determines loan eligibility based on three criteria: age, monthly income, and credit score. It provides specific reasons if the loan application is denied.
- **Age:** Must be 21 or older.
- **Income:** Must be at least $30,000 monthly.
- **Credit Score:** Must be 650 or higher.

```python
def check_loan_eligibility(age, monthly_Income, credit_score):
    rejection_cause = []
    if age < 21 :
        rejection_cause.append("Age less than 21")
    if monthly_Income < 30000:
        rejection_cause.append("Income less than 30000")
    if credit_score < 650:
        rejection_cause.append("Credit score less than 650")
    return rejection_cause
```

#### 6. Greatest Common Divisor (GCD) Calculator
Implementation of the Euclidean algorithm to find the greatest common divisor of two integers provided by the user.

```python
def GCD(a, b):
    while b:
        a, b = b, a % b
    return a
```

## How to Run

To run the lab exercises, you will need to have Python and Jupyter Notebook installed.

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/ronnin796/ai_labs.git
    cd ai_labs
    ```

2.  **Install Jupyter:**
    If you don't have Jupyter installed, you can install it using pip:
    ```sh
    pip install jupyterlab
    ```

3.  **Launch Jupyter and open the notebook:**
    ```sh
    jupyter lab Lab1.ipynb
    ```
    This will open the notebook in your web browser, where you can run each code cell individually.
