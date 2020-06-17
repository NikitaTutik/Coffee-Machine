# Coffee-Machine
Coffee Machine written on Python :)
 
import sys

class CoffeeMachine:
    
    
    def __init__(self, water, milk, coffee_beans, disposable_cups, money):
        self.water = water
        self.milk = milk
        self.coffee_beans = coffee_beans
        self.disposable_cups = disposable_cups
        self.money = money


    def remaining(self):
        print("The coffee machine has:")
        print(self.water, " of water")
        print(self.milk, " of milk")
        print(self.coffee_beans, " of coffee beans")
        print(self.disposable_cups, " of disposable cups")
        print("$" + str(self.money), " of money")
        print()


    def menu(self):
        loop = True
        while loop:
            action = input("Write action (buy, fill, take, remaining, exit):\n")
            if action == "buy":
                print()
                self.buy()
            elif action == "fill":
                print()
                self.fill()
            elif action == "take":
                print()
                self.take_money()
            elif action == "remaining":
                print()
                self.remaining()
            elif action == "exit":
                exit()
            else:
                print("Wrong action")


    def buy(self):  # function for buying coffee
        print()
        type_ = input('What do you want to buy? 1 - espresso, 2 - latte, 3 - cappuccino, back - to main menu:\n> ').strip()
        if type_ == '1':
            if self.water < 250:
                print('Sorry, not enough water!')
            elif self.coffee_beans < 16:
                print('Sorry, not enough coffee beans!')
            elif self.disposable_cups < 1:
                print('Sorry, not enough disposable cups!')
            else:
                print('I have enough resources, making you a coffee!')
                self.water -= 250
                self.coffee_beans -= 16
                self.disposable_cups -= 1
                self.money += 4
        elif type_ == '2':
            if self.water < 350:
                print('Sorry, not enough water!')
            elif self.milk < 75:
                print('Sorry, not enough milk!')
            elif self.coffee_beans < 20:
                print('Sorry, not enough coffee beans!')
            elif self.disposable_cups < 1:
                print('Sorry, not enough disposable cups!')
            else:
                print('I have enough resources, making you a coffee!')
                self.water -= 350
                self.milk -= 75
                self.coffee_beans -= 20
                self.disposable_cups -= 1
                self.money += 7
        elif type_ == '3':
            if self.water < 200:
                print('Sorry, not enough water!')
            elif self.milk < 100:
                print('Sorry, not enough milk!')
            elif self.coffee_beans < 12:
                print('Sorry, not enough coffee beans!')
            elif self.disposable_cups < 1:
                print('Sorry, not enough disposable cups!')
            else:
                print('I have enough resources, making you a coffee!')
                self.water -= 200
                self.milk -= 100
                self.coffee_beans -= 12
                self.disposable_cups -= 1
                self.money += 6
        else:
            print()


    def fill(self):
    
        print("Write how many ml of water do you want to add: ")
        self.water += int(input())
        print("Write how many ml of milk do you want to add: ")
        self.milk += int(input())
        print("Write how many grams of coffee beans do you want to add: ")
        self.coffee_beans += int(input())
        print("Write how many grams of coffee beans do you want to add: ")
        self.disposable_cups += int(input())
        print()


    def take_money(self):
        
        print("I gave you $" + str(self.money))
        print()
        self.money = 0


    def exit():
        sys.exit()


coffee_machine = CoffeeMachine(400, 540, 120, 9, 550)
coffee_machine.menu()
