#coffee_machine
water = 400
milk = 540
coffee_bean = 120
disposable_cups = 9
money = 550

#def sentence():
    #global water, milk, coffee_bean,disposable_cups, money
    #print(f"""
#The coffee machine has:
#{water} ml of water 
#{milk} ml of milk 
#{coffee_bean} g of coffee beans
#{disposable_cups} disposable cups
#{money} of money""")
    
def espresso():
    global water, milk, coffee_bean, disposable_cups,money
    if water > 250:
        print("I have eough resources")
        water -= 250
        milk = milk 
        coffee_bean -= 16
        disposable_cups -= 1
        money += 4
    else:
        print("Not enough water")
        
    
def latte():
    global water, milk, coffee_bean, disposable_cups, money
    if water > 350:
        print("I have enough resources making coffee")
        water -= 350
        milk -= 75
        coffee_bean -= 20
        disposable_cups -= 1
        money += 7
    else:
        print("Sorry not enough water!")
        

def cappuccino():
    global water , milk, coffee_bean, disposable_cups,money
    if water >=200:
        print("I have enough resources, making you a coffee!")
        water -=  200
        milk -= 100
        coffee_bean -= 12
        disposable_cups -= 1
        money += 6
    else:
        print("Sorry, not enough water!")
        

def fill():
    global water,milk, coffee_bean, disposable_cups,money
    water_input = int(input("How many ml of water to you want to add? :"))
    milk_input = int(input("How many ml of milk do you want to add?: "))
    bean_input = int(input("How many gram of coffee bean do you want to add?: "))
    cup_input = int(input("How many cups do you want to add"))
    water += water_input
    milk += milk_input
    coffee_bean += bean_input
    disposable_cups += cup_input
    
def take():
    global water,milk, coffee_bean, disposable_cups,money
    print("I gave you ${}".format(money))
    money -= money

def remaining():
    global water, milk, coffee_bean, disposable_cups,money
    return print(f"""
The coffee machine has:
{water} ml of water 
{milk} ml of milk 
{coffee_bean} g of coffee beans
{disposable_cups} disposable cups
${money} of money""")
    
action = input("Would you like to buy, fill or take, remaining, exit?: ")
while True:
    #action = input("Would you like to buy, fill or take, remaining, exit?, back-to the main menu: ")
    if action == 'back':
        action = input("Would you like to buy, fill or take, remaining, exit?: ")
        print()


    if action  == 'buy':
        buy = input("what do you want to buy? 1 - espresso, 2 - latte, 3 - cappuccino: ")
        if buy == "back":
            action = input("Would you like to buy, fill or take, remaining, exit?: ")
            
        if buy.isnumeric():
            buy = int(buy)
        if buy == 1:
            espresso()
            print()
            action = input("Would you like to buy, fill or take, remaining, exit?, back-to the main menu: ")
        elif buy == 2:
            latte()
            print()
            action = input("Would you like to buy, fill or take, remaining, exit?, back-to the main menu: ")
        elif buy == 3:
            cappuccino()
            action = input("Would you like to buy, fill or take, remaining, exit?, back-to the main menu: ")
    if action == "fill":
        fill()
        action = input("Would you like to buy, fill or take, remaining, exit?, back-to the main menu: ")
    if action == "take":
        take()
        action = input("Would you like to buy, fill or take, remaining, exit?, back-to the main menu: ")
    if action == "remaining":
        remaining()
        print()
        action = input("Would you like to buy, fill or take, remaining, exit?, back-to the main menu: ")
    if action == "exit":
            break
