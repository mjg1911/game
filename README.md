import random

number = random.randint(1, 2000)
tries = 0
win = False # setting a win flag to false



name = input("Hello, What is your username? ")
age = input ("And what is your age? ")

if name =="admin":
    print("")
    print ("the number your looking for is {}" .format(number))
else:
    print("")
    print ("Hello " + name +', dont you think  '+ age + " is a bit old to play Python games.")


print("")
print("")
question = input("Would you still like to play "+ name +"....? [Y/N] ")
if question.lower() == "n": #in case of capital letters is entered
    print("oh..okay")
    exit()
if question.lower() == "y":
    print("I'm thinking of a number between 1 & 2000")
    print("")
if question.lower() == "cheat":
        print("WOW really.... cheating.... oke the number is: {}".format(number))
        question = input("Are you sure you still wana play " + name + "? [Y/N] ")
        print("")
        if question.lower() >= "n":  # in case of capital letters is entered
            print("oh..okay")
            input('Press ENTER to exit')
            exit()
        if question.lower() == "y":
            print("I'm thinking of a number between 1 & 20")
            print("")

while not win:       # while the win is not true, run the while loop. We set win to false at the start therefore this will always run
    guess = int(input("Have a guess: "))
    tries = tries + 1
    if guess == number:
        win = True    # set win to true when the user guesses correctly.
    elif guess < number:
        print("Guess Higher")
    elif guess > number:
        print("Guess Lower")
# if win is true then output message
if name =="admin":
    print("")
    print ("as admin its not hard to win now is it")
    input('Press ENTER to exit')
else:
    print("Congrats, you guessed correctly. The number was indeed {}".format(number))
    print("it had taken you {0} tries not bad for someone thats {1} years old".format(tries,age))
    input('Press ENTER to exit')
