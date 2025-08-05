# Intro to Python Assignment: Responsive Calculator Program for Ronald Okumu

def get_number(prompt):
    """Prompt the user for a number and validate input."""
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("❌ Invalid input. Please enter a valid number.")

def get_operation():
    """Prompt the user to choose a valid mathematical operation."""
    operations = ['+', '-', '*', '/']
    while True:
        op = input("🔢 Choose an operation (+, -, *, /): ").strip()
        if op in operations:
            return op
        else:
            print("❌ Invalid operation. Please choose one of +, -, *, /.")

def calculate(num1, num2, operation):
    """Perform the calculation based on the chosen operation."""
    if operation == '+':
        return num1 + num2
    elif operation == '-':
        return num1 - num2
    elif operation == '*':
        return num1 * num2
    elif operation == '/':
        if num2 == 0:
            return "⚠️ Error: Division by zero is not allowed."
        else:
            return num1 / num2

def main():
    print("👋 Welcome to Ronald Okumu's Python Calculator Assignment!")
    print("Let's perform a simple calculation step-by-step.\n")

    # Step 1: Get two numbers from the user
    num1 = get_number("🔸 Enter the first number: ")
    num2 = get_number("🔸 Enter the second number: ")

    # Step 2: Get the operation
    operation = get_operation()

    # Step 3: Perform the calculation
    result = calculate(num1, num2, operation)

    # Step 4: Display the result
    if isinstance(result, str):
        print(result)
    else:
        print(f"\n✅ Result: {num1} {operation} {num2} = {result}")

# Run the calculator
main()
