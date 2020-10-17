# chatbot

"""
This is a program for a chat bot...
1.The bot will start with a greeting and self intro and ask for name of the person
2.The bot will greet and welcome the person
3.Bot will ask what a person want to do,it will offer a choice of things based upon what the bot is designed for
4.It eill respond to users input appropiately
"""
import random
from datetime import datetime
def greet_and_introduce():
    #declare some list of responses
    responses = [    
        "Hi There! I am bot. can help you do some calculations.",
        "Wonderful, It is so nice to be in touch with you."
    ] 
    #pick a response at random and return that
    return random.choice(responses)   

def welcome(name):
    messages = [
        "Nice to meet you",
        "Lets have some good time together"
    ]
def get_timeofday_greeting():
    current_time = datetime.now()
    timeofday_greeting = "Good Morning"
    if current_time.hour > 12 and current_time.hour<17:
        timeofday_greeting = "Good Afternoon"
    elif current_time.hour >= 17 and current_time.hour <22:
        timeofday_greeting = "Good Evening"
    elif current_time.hour >= 22:
        timeofday_greeting = "Hi, THat's late"
    return timeofday_greeting
    

def welcome(name):
    messages = [
        "Nice to meet you",
        "Lets have some good time together"
    ]

    print(f"{get_timeofday_greeting()}, {random.choice(messages)}")

def show_menu():
    print("1. calculate an expression")
    print("2. get current time")
    print("3. End this chat")
    print("----------------")
    try:
        return int(input("Enter your choice [1-3]: "))
    except:
        print("Only enter choice from 1, 2 and 3")
        return 0
def evaluate_expression():
    expr=input("Enter an expression: ")
    try:
        print("Result = ", eval(expr))
    except Exception as e:
        print(str(e))

def bot():
    greet_and_introduce()
    name = input("your name: ")
    welcome(name)
    choice=show_menu()
    while choice !=3:
        if (choice==1):
            evaluate_expression()
        elif(choice==2):
            print(str(datetime.now()))
        else:
            print("I dont understand that")
            choice=show_menu()
        choice=show_menu()


bot()
