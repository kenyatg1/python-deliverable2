print("Welcome to the GC Fruit Market.")
name = input("What is your name? ")
print("\n")
fruits = ["Apple", "Grape", "Orange"]
receipt = []
print(f"Welcome, {name}. Which Fruit would you like to buy?")
print(f"1. {fruits[0]}  $2")
print(f"2. {fruits[1]}  $1")
print(f"3. {fruits[2]} $3")
purchases = input("> ")
index = int(purchases) - 1
if purchases == "1":
    print(f"You bought 1 Apple at $2")
    purchases = "Apple"
elif purchases == "2":
    print(f"You bought 1 Grape at $1")
    purchases = "Grape"
elif purchases == "3":
    Orange_num = print(f"You bought 1 Orange at $3")
    purchases = "Orange"
while True:
    receipt.append(purchases)
    more_fruit = input(f"{name}, would you like to buy another piece of fruit? y/n ")
    if more_fruit == "y" or more_fruit == "Yes" or more_fruit == "yes":
        print(f"Which Fruit would you like to buy, {name}?")
        print(f"1. {fruits[0]}  $2")
        print(f"2. {fruits[1]}  $1")
        print(f"3. {fruits[2]} $3")
        purchases = (input("> "))
        if purchases == "1":
            print(f"You bought 1 Apple at $2")
            purchases = "Apple"
        elif purchases == "2":
            print(f"You bought 1 Grape at $1")
            purchases = "Grape"
        elif purchases == "3":
            print(f"You bought 1 Orange at $3")
            purchases = "Orange"
    else:
        break
print("\n")
totApples = int(receipt.count("Apple"))
totGrapes = int(receipt.count("Grape"))
totOranges = int(receipt.count("Orange"))
print(f"Receipt for {name}:")
print(f"{totApples} apple(s) at $2")
print(f"{totGrapes} grape(s) at $1")
print(f"{totOranges} oranges(s) at $3")
granApples = totApples * 2
granOranges = totOranges * 3
subtotal = granApples + granOranges + totGrapes
print(f"Sub Total                               ${subtotal}")
tax = round(.0825 * subtotal, 2)
print(f"Tax                8.25%                {tax}")
grandtotal = round(tax + subtotal, 2)
print(f"                                        ${grandtotal}")
print("\n")
print(f"Thank you, {name} for shopping! :-)")

