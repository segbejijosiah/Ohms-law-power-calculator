

# ==========================================
# OHM'S LAW AND POWER CALCULATOR
# ==========================================

# Store previous calculations
history = []


# Function to get valid positive numbers
def get_number(message):

    while True:

        try:
            number = float(input(message))

            if number <= 0:
                print("Error: Enter a number greater than zero.")

            else:
                return number

        except ValueError:
            print("Invalid input! Please enter a valid number.")


# Function to display calculation history
def show_history():

    print("\n========== CALCULATION HISTORY ==========")

    if len(history) == 0:
        print("No calculations available.")

    else:
        for number, item in enumerate(history, start=1):
            print(f"{number}. {item}")


# Function to clear calculation history
def clear_history():

    if len(history) == 0:
        print("There is no history to clear.")

    else:
        confirm = input("Are you sure you want to clear history? (yes/no): ")

        if confirm.lower() == "yes":
            history.clear()
            print("Calculation history cleared.")

        else:
            print("History was not cleared.")


# Keep the calculator running
while True:

    print("\n========================================")
    print("      OHM'S LAW AND POWER CALCULATOR")
    print("========================================")

    print("1. Calculate Voltage")
    print("2. Calculate Current")
    print("3. Calculate Resistance")
    print("4. Calculate Electrical Power")
    print("5. View Calculation History")
    print("6. Clear Calculation History")
    print("7. Exit")

    choice = input("\nEnter your choice (1-7): ")

    # Calculate voltage
    if choice == "1":

        current = get_number("Enter current (A): ")
        resistance = get_number("Enter resistance (Ohms): ")

        voltage = current * resistance

        result = (
            f"Voltage: {current} A x {resistance} Ohms "
            f"= {voltage:.2f} V"
        )

        print("\nCalculated Answer:")
        print(f"Voltage = {voltage:.2f} Volts (V)")

        history.append(result)

    # Calculate current
    elif choice == "2":

        voltage = get_number("Enter voltage (V): ")
        resistance = get_number("Enter resistance (Ohms): ")

        current = voltage / resistance

        result = (
            f"Current: {voltage} V / {resistance} Ohms "
            f"= {current:.2f} A"
        )

        print("\nCalculated Answer:")
        print(f"Current = {current:.2f} Amperes (A)")

        history.append(result)

    # Calculate resistance
    elif choice == "3":

        voltage = get_number("Enter voltage (V): ")
        current = get_number("Enter current (A): ")

        resistance = voltage / current

        result = (
            f"Resistance: {voltage} V / {current} A "
            f"= {resistance:.2f} Ohms"
        )

        print("\nCalculated Answer:")
        print(f"Resistance = {resistance:.2f} Ohms (Ω)")

        history.append(result)

    # Calculate power
    elif choice == "4":

        voltage = get_number("Enter voltage (V): ")
        current = get_number("Enter current (A): ")

        power = voltage * current

        result = (
            f"Power: {voltage} V x {current} A "
            f"= {power:.2f} W"
        )

        print("\nCalculated Answer:")
        print(f"Power = {power:.2f} Watts (W)")

        history.append(result)

    # View history
    elif choice == "5":

        show_history()

    # Clear history
    elif choice == "6":

        clear_history()

    # Exit
    elif choice == "7":

        print("\nThank you for using")
        print("OHM'S LAW AND POWER CALCULATOR!")
        print("Goodbye!")
        break

    # Invalid menu choice
    else:

        print("Invalid choice! Please select a number from 1 to 7.")
