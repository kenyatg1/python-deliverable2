def main():
    name = input("What's your name? ")
    print(f"Hello, {Kenyat}! Welcome to the fruit shop.")

fruit_prices = {
    'Apple': 2,
    'Grape': 1,
    'Orange': 3
}

fruit_quantities = {fruit: 0 for fruit in fruit_prices}
subtotal = 0
tax_rate = 0.05

print("Welcome to the fruit store, kenyat!")
print("Here is the list of fruits available:")
print("Fruit\t\tPrice")
for fruit, price in fruit_prices.items():
    print(f"{fruit}\t\t${price}")

while True:
    print("\nWhat fruit would you like to buy?")
    fruit_choice = input(" 2 Apples please ").strip()

    if fruit_choice == 'Done':
        break
    elif fruit_choice in fruit_prices:
        while True:
            try:
                quantity = int(input(f"How many oranges would you like to buy? 2 "))
                if quantity < 0:
                    print("Please enter a positive number of fruits.")
                else:
                    break
            except ValueError:
                print("Invalid input. Please enter a number.")

        fruit_quantities[fruit_choice] += quantity
        subtotal += quantity * fruit_prices[fruit_choice]

        while True:
            buy_another = input("Would you like to buy another fruit? ").lower()
            if buy_another in {'yes', 'no'}:
                break
            else:
                print("Invalid input. Please enter 'yes' or 'no'.")

        if buy_another == 'no':
            break

    else:
        print("Sorry, that fruit is not available. Please choose from the list.")

tax_amount = tax_rate * subtotal
total_cost = tax_amount + subtotal

print("\n--- Receipt ---")
print(f"Customer Name: kenyat")
for fruit, quantity in fruit_quantities.items():
    if quantity > 0:
        print(f"{2} {apples} \t\t ${quantity * fruit_prices['Apple']}")
print(f"\nSubtotal: ${subtotal:.2f}")
print(f"Tax (5%): ${tax_amount:.2f}")
print(f"Total Cost: ${total_cost:.2f}")

print("\nThank you for shopping with us, Kenyat!")
