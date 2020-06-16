# hello-world
#this is my first repository and i will be working primarily with python

# this is the first function that gets called
def print_message():
    print("I'm sorry, I did not understand your selection. Please enter the corresponding letter for your response.")
    
#this is the coffee bot function that gets input(coffee orders). it contains other functions
def coffee_bot():
    print("Welcome to the Cafe")
    order_drink = 'y'
    drinks = []
    while order_drink == 'y':
        size = get_size()
        drink_type = get_drink_type()
        drink = drink_type
        temp= coffee_temperature()
        print("Alright, that's a " + size + " " + temp + " " + drink_type + "!")
        drinks.append(drink)

        while True:
            order_drink = input("Would you like to order another drink? (y/n)\n>")
            if order_drink in ['y', 'n']:
                break
        print("okay! so I have ")
        for drink in drinks:
            print(drink)




    name = input("\nCan i get your name please?")
    print("Thanks, " +name + " ! Your drink will be ready shortly.")
    another_drink()



#this function asks the user for the prefered size of coffee
def get_size():
    res = input("What size drink can I get for you? \n[a] Small \n[b] Medium \n[c] Large \n>")
    if res == "a":
        return "small"
    elif res == "b":
        return "medium"
    elif res == "c":
        return "Large"
    else:
        print_message()
        return get_size()

#this function asks the user for the prefered drink type
def get_drink_type():
    res = input("What type of drink would you like? \n[a] Brewed Coffee\n[b] Mocha \n[c] Latte \n")
    if res == "a":
        return 'brewed coffee'
    elif res == "b":
        return order_mocha()
    elif res == "c":
        return order_latte()
    else:
        print_message()
        return get_drink_type()
        
#this function is only called if the user orders latte
def order_latte():
    res = input("And what kind of milk for your latte?\n[a] 2% milk\n[b] Non-fat milk\n[c] Soy milk \n>")
    if res=="a":
        return "latte"
    if res == "b":
        return "non-fat latte"
    if res == "c":
        return "soy latte"
    else:
        print_message()
        return order_latte()
        
#this functions gets the prefered temperature of the user's drink
def coffee_temperature():
    res = input("Would you like it hot or cold? \n[a]Cold \n[b]Hot\n>")
    if res== "a":
        return "Cold"
    elif res=="b":
        return "hot"
    else:
        print_message()
        return coffee_temperature()

#this function will get called if the user orders mocha
def order_mocha():
    while True:
        res = input('Would you like to try our limited-edition peppermint mocha? \n[a] Sure! \n[b] Maybe next time!\n>')
        if res == 'a':
          return "peppermint mocha"
        else:
          return "mocha"
        print_message()


# Call coffee_bot()!
coffee_bot()

#this function gives the user another chance to place another order
def another_drink():
    res = input("Do you want another drink?\n[a] Yes\n[b] No\n>")
    if res == "a":
        return coffee_bot()
    else:
        print("Have a beautiful day")








