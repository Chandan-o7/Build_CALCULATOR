# Task 1: Build Calculator

# Functions for basic arithmetic
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    try:
        return a / b
    except ZeroDivisionError:
        return "Error: Division by zero is not allowed."

# Main calculator loop
def calculator():
    print("Welcome to the Command-Line Calculator!")
    print("Operations: + for addition, - for subtraction, * for multiplication, / for division")
    
    while True:
        try:
            num1 = float(input("\nEnter the first number: "))
            operator = input("Enter operator (+, -, *, /): ")
            num2 = float(input("Enter the second number: "))

            if operator == "+":
                result = add(num1, num2)
            elif operator == "-":
                result = subtract(num1, num2)
            elif operator == "*":
                result = multiply(num1, num2)
            elif operator == "/":
                result = divide(num1, num2)
            else:
                print("Invalid operator! Please use +, -, *, or /")
                continue

            print(f"Result: {num1} {operator} {num2} = {result}")

        except ValueError:
            print("Error: Please enter valid numeric values.")

        choice = input("Do you want to perform another calculation? (yes/no): ").lower()
        if choice != "yes":
            print("Exiting Calculator. Goodbye!")
            break
if __name__ == "__main__":
    calculator()
