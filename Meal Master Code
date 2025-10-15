""" Meal Master - Online Restaurant Booking System  
A Python-based project to book and manage restaurant reservations.  
Handles user input, prevents double bookings, and stores reservation data.  
Designed for easy use and real-world learning. """

food = {
    'Breakfast': {
        '1 dozen eggs': {'Price': 6.00, 'Stock': 9},
        'loaf of bread': {'Price': 3.50, 'Stock': 15},
        'breakfast cereal': {'Price': 4.50, 'Stock': 10},
        'pancakes with syrup': {'Price': 12.00, 'Stock': 6},
        'all Canadian Breakfast platter': {'Price': 9.99, 'Stock': 5},
        'hash browns': {'Price': 10.00, 'Stock': 8}
    },
    'Lunch': {
        'simple sandwich + drink': {'Price': 15.00, 'Stock': 12},
        'fast food combo (burger, fries, drink)': {'Price': 12.00, 'Stock': 20},
        'salad bowl': {'Price': 14.00, 'Stock': 10},
        'chicken breast': {'Price': 13.00, 'Stock': 8}
    },
    'Dinner': {
        'main dish at inexpensive restaurant': {'Price': 25.00, 'Stock': 6},
        'mid-range restaurant dinner': {'Price': 40.00, 'Stock': 4},
        'steak dinner': {'Price': 45.00, 'Stock': 5},
        'ground beef': {'Price': 15.00, 'Stock': 10}
    }
} # The menu (dict) for Meal Master
table_number = {'Table 1': 'Occupied','Table 2': 'Not Occupied','Table 3': 'Not Occupied', 'Table 4': 'Not Occupied',
                'Table 5': 'Occupied','Table 6': 'Not Occupied','Table 7': 'Not Occupied', 'Table 8': 'Not Occupied',
                'Table 9': 'Not Occupied'}
name = str(input('Enter your full name: '))
number = str(input('Book a table number from 1 to 9: '))
num = 0
lst = ['1','2','3','4','5','6','7','8','9'] #Table numbers
num1 = 0

while num != 1:
    for i in table_number.keys():
        if number in i:
            if table_number[i] == 'Not Occupied':
                print('Succesfully booked!!!')
                num+=1
            else:
                print('Table is already booked.')
                number = str(input('Book again: '))
        elif number not in lst:
            print('The Table you have book does not exist. ')
            number = str(input('Book again: '))
        # Table booking in Meal Master - successful or not successful
print('Welcome To Meal Master Restaurant: ')
menu = str(input('What would you like to have- Breakfast, Lunch, Dinner: '))# 3 different menu in Meal Master
menu = menu.lower()
menu = menu.replace(menu[0],menu[0].upper())
menu = menu.strip()
num =  0
lst = []

class Customer:
    def breakfast(self,items):
        for i in range(1,items+1):
            i = str(i)
            order = str(input('Enter item'+ ' ' +i+': '))
            order = order.strip()
            order = order.lower()
            net = 0
            while net != 7:
                if order in food[menu].keys():
                    net+=7
                else:
                    print('The item you have entered is not in the menu.')
                    order = str(input('Enter item'+ ' ' +i+' '+ 'again : '))
            lst.append(order)      # #
        # The functons takes oeder from breakfast menu.
    def lunch(self,items):
        for i in range(1,items+1):
            i = str(i)
            order = str(input('Enter item'+ ' ' +i+': '))
            order = order.lower()
            order = order.strip()
            net = 0
            while net != 7:
                if order in food[menu].keys():
                    net+=7
                else:
                    print('The item you have entered is not in the menu.')
                    order = str(input('Enter item'+ ' ' +i+' '+ 'again : '))
            lst.append(order)
        # The functons takes order from lunch menu.
    def dinner(self,items):
        for i in range(1,items+1):
            i = str(i)
            order = str(input('Enter item'+ ' ' +i+': '))
            order = order.lower()
            order = order.strip()
            net = 0
            while net != 7:
                if order in food[menu].keys():
                    net+=7
                else:
                    print('The item you have entered is not in the menu.')
                    order = str(input('Enter item'+ ' ' +i+' '+ 'again : '))
            lst.append(order)
p1 = Customer()
        # The functons takes order from dinner menu.
while num != 7:
    if menu == 'Breakfast':
        print('Here is the menu for breakfast: ')
        for i in food['Breakfast'].keys():
            print('->',i)
        items = int(input('How many items would you like to buy: '))
        p1.breakfast(items)
        num+=7
    elif menu == 'Lunch':
        print('Here is the menu for lunch: ')
        for i in food['Lunch'].keys():
            print('->',i)
        items = int(input('How many items would you like to buy: '))
        p1.lunch(items)
        num+=7
    elif menu == 'Dinner':
        print('Here is the menu for dinner: ')
        for i in food['Dinner'].keys():
            print('->',i)
        items = int(input('How many items would you like to buy: '))
        p1.dinner(items)
        num+=7
    else:
        print('Error, Choose again.')
        menu = str(input('What would you like to have- Breakfast, Lunch, Dinner: '))
        menu = menu.lower()
        menu = menu.replace(menu[0],menu[0].upper())
        menu = menu.strip()
# Prints menu
class Restaurant:
    def __init__(self,customer_name,bill):
        self.name = customer_name
        self.bill = bill
    def order(self):
        for i in lst:
            food[menu][i]['Stock'] -=1
            self.bill+= food[menu][i]['Price']
    def tax(self):
        self.bill += round(13/100*self.bill)
    def win(self):
        self.bill/=2
        self.bill+=5
    def lose(self):
        self.bill+=5

p1 = Restaurant(name,0)
p1.order()
p1.tax()
# Takes backhand order, saves the price in the bill and reduce each stock by 1, and prints bill along with taxes


print(name, 'You have been exclusivly selected for an invitation to a lucky draw taking place today that could '
                'reduce you bill up to 50%. To join you need to pay $5.')

sure = str(input('Would you like to participate: '))
sure = sure.lower()
sure = sure.strip()
num = 0

while num != 1:
    if sure == 'yes':
        if sure == 'yes':
            print('How to play: You guess a number from 0 to 10, if the number is the very number that was selected by our chif guest Sam, you will win a discout of 50% in your bill! ')
        guess = int(input('Enter you lucky guess: '))
        if guess == 2:
            print('Congragulations!!!, you won 🥳🥳.')
            print('Meal Maker Bill: ')
            p1.win()
            for i in lst:
                print(i,' = ', food[menu][i]['Price'])
            print('Tax = 0.13%')
            print('Particpation fee for the lucky draw = $5')
            print(name,'Your total bill including 50% dicount is', p1.bill)
            num+=1
        else:
            p1.lose()
            print('Sorry, you lost but better luck next time!!!')
            for i in lst:
                print(i,' = ', food[menu][i]['Price'])
            print('Tax = 0.13%')
            print('Particpation fee = $5')
            print(p1.bill)
            num+=1
    else:
        print('Meal Maker Bill: ')
        for i in lst:
            print(i,' = ', food[menu][i]['Price'])
        print('Tax = 0.13%')
        print(name,'Your total bill including tax is', p1.bill)
        num+=1
        # Lucky draw that can reduce their bill up to 50 percentage

#Payment_Method
payment_Method = str(input('Would you like to pay by credit or debit: '))
payment_Method = payment_Method.lower()
payment_Method = payment_Method.strip()
if payment_Method == 'credit':
    a = str(input('Enter you password: '))
    b = str(input('Rate us between 1 to 5: '))
    print('Thank you for your feedback. ')
elif  payment_Method == 'debit':
    a = str(input('Enter you password: '))
    b = str(input('Rate us between 1 to 5: '))
    print('Thank you for your feedback. ')
