# Rock Paper Scissors
Repo for the project based approach of Intro to Python Bootcamp.

- [Rock Paper Scissors](#rock-paper-scissors)
  - [Introduction](#introduction)
  - [Playing the game in Python](#playing-the-game-in-python)
  - [Before Starting](#before-starting)
  - [Week 1](#week-1)
  - [Week 2](#week-2)
  - [Week 3](#week-3)
    - [If ... Else](#if--else)
  - [Week 4](#week-4)
  - [Week 5](#week-5)

## Introduction

In this project we are going to do a simple implementation of the game "Rock Paper Scissors" (aka **Schere, Stein, Papier** in German).
It is a game that can be played between two or more players. The players can choose either “rock, paper, scissors”. Then each of the players simultaneously makes their hands in the shapes of Rock Paper Scissors.
Some of you who might not know the game can check the [Wikipedia](https://en.wikipedia.org/wiki/Rock_paper_scissors) or this hilarious [Wikihow](https://www.wikihow.com/Play-Rock,-Paper,-Scissors). The game will be played in the command line interface.

The winner is selected based on the following:

- Rock smashes scissors
- Paper covers rock
- Scissors cut paper

## Playing the game in Python
- Take User Input
- Make the Computer Choose
- Determine a Winner



## Before Starting

1. Set up the project location using Google Colab where you will be doing the project. 
2. Test by using `print("Hello, World!")` (you know, for good luck 😊).
3. Commit and push your changes to the repository of your project.

## Week 1

Since in the first week we only learn to set up the development environment and did the Hello World exercise, we are going to implement the introduction message when we start the project program. It can be something as simple as 
```
Welcome to the game of Rock Paper Scissors.
```
or it can be as epic as
```
The year is 20xx. The world is overrun by rogue AIs. You are now face to face with the hive mind of all the AIs, the RPS. The world hangs in balance on the game of Rock Paper Scissors that you are going to play against RPS.
```
It is up to you how you want to introduce to the player that runs your project.

Code snippet for this week:
```python
print("Welcome to the game of Rock Paper Scissors.")
print("The winning rules for the game are as follows:\n"
                                +"   "+"Rock vs Paper    -> Paper wins\n"
                                +"   "+"Rock vs Scissors  -> Rock wins\n"
                                +"   "+"Paper vs Scissors -> Scissors wins\n")
```

## Week 2

Now that we've learnt about Variables and Booleans in week two, we are going to introduce these two elements into our project. We will add variables for the player's choice and also the computer's choice.

Code snippet:
```python
player_choice = "rock"# If player choice is rock and computer choice is paper then rock vs paper -> paper wins
computer_choice = "paper" # Good ol rock, nothing beats that

player_choice = "rock" #If player choice is rock and computer choice is scissors then rock vs scissors -> rock wins
computer_choice = "scissors"

player_choice = "paper" #If player choice is paper and computer choice is scissors then paper vs scissors -> scissors wins
computer_choice = "scissors"

print("Player's choice: " + player_choice)
print("Computer's choice: " + computer_choice)
```

Since we have learned about Booleans in week two, we can also use booleans as a way to keep track of whether the player won or not.

Code snippet:
```python
is_player_win = True
print("Player win status: " + str(is_player_win))  #this will print True, we have to typecast to string
```

We can then structure the whole code to be more organized. The code snippet up to this point should look something like below.

Code snippet for this week:
```python
# variable declaration
player_choice = "rock"
computer_choice = "paper" # Good ol rock, nothing beats that
is_player_win = False
is_computer_win= True

# display message
print("Welcome to the game of Rock Paper Scissors.")

# display choices
print("Player's choice: " + player_choice)
print("Computer's choice: " + computer_choice)

# display who wins
print("Is player wins:",is_player_win)
print("Is computer wins: ",is_computer_win)
```

## Week 3

In this week we learnt about loops, operators and conditions and we will introduce them to our project up to this point. We also learnt about functions, then we can introduce them to the project as well.

For the loops, we are going to use it to control how many rounds are played. We will also use operators to manipulate the round number and we use condition to determine when the while loop is exited.

### If ... Else
Using the If and else statement we can play the game statically.

```python
choice1 = "rock"
choice2 = "paper"
choice3 = "scissors"
player_choice = ""#You can assign for this variable (rock, paper, scissors)
computer_choice = ""#You can assign for this variable (rock, paper, scissors)

if player_choice == "rock":
  if computer_choice == "paper":
     print("The winner is:", choice2)
if player_choice == "rock":
   if computer_choice == "scissors":
        print("The winner is:", choice1)
elif player_choice == "paper":
  if computer_choice == "scissors":
    print("The winner is:", choice3)
```

Code snippet:

```python
current_round = 0
number_of_rounds = 3

while current_round != number_of_rounds: # while loop with condition
  print("Current round: " + str(current_round + 1))
  current_round = current_round + 1 # operator to manipulate the round number
```

As for function, we are going to make a function where the computer will make it's choice to play against the player.

Code snippet:
```python
def computer_play():
  return "rock" # Good ol rock, nothing beats that
```

We can then combine the code snippets below with the rest of our code.

Code snippet for this week:
```python
# variable declaration
player_choice = "paper"
is_player_win = True
current_round = 0
number_of_rounds = 3

def computer_play():
  return "rock" # Good ol rock, nothing beats that

# display message
print("Welcome to the game of Rock Paper Scissors.")

while current_round != number_of_rounds: # while loop with condition
  print("Current round: " + str(current_round + 1)) # we should show 1 instead of 0 for the first round
  computer_choice = computer_play()

  # display choices
  print("Player's choice: " + player_choice)
  print("Computer's choice: " + computer_choice)

  current_round = current_round + 1 # operator to manipulate the round number

# display whether player wins
print("Player win status: " + str(is_player_win)) #this will print True, we have to typecast to string
```

## Week 4
As for week four, we learned how to use the python library and how to import module.Now here based on the need of the project we import the random module.
Python Random module is an in-built module of Python which is used to generate random numbers.It returns a random number between 0.0 and 1.0.

Code snippet:
``` python
import random
print(random.random())

```
As the game is played between two players, one is the user and the other is the computer. For the computer to make the selection, we need to use the random() module, that the (rock, paper, scissors) could be selected randomly.

Code snippet for this week:
``` python
# import random module
import random
# display message
print("Welcome to the game of Rock Paper Scissors.")

#runs without any conditions until the break statement executes inside the loop.
while True:
	print("Enter your choice \n 1 for Rock \n 2 for Paper \n 3 for Scissors \n")
 
 	# take the input from the user for making a selection
	player_choice = int(input("Player's turn: "))
 
 #looping until user enter invalid input
	while player_choice > 3 or player_choice < 1:
		player_choice = int(input("Your input is not valid, please enter a value between 1,3: "))
		
	if player_choice == 1:
		player_select = 'rock'
	elif player_choice == 2:
		player_select = 'paper'
	else:
		player_select = 'scissors'

  # print user choice
	print("The user has selected: " + player_select.capitalize())
	print("\nComputer's turn.......")
 
 #We make a specific interval that the computer choose a random  number between (1,3)
	computer_choice = random.randint(1, 3)

# It is okay if the computer makes the same choice

	if computer_choice == 1:
		computer_select = 'rock'
	elif computer_choice == 2:
		computer_select = 'paper'
	else:
		computer_select= 'scissors'
		
	print("Computer has selected: " + computer_select.capitalize())

	print(player_select.capitalize() + " Vs " + computer_select.capitalize())
 #for ending the loop
	break
``` 

## Week 5

Home stretch. We are going to clean up and put some final touches to the game so that we can play it. First we will define a function for the computer to make the choice.

Code snippet:
```python
import random

# global variable
computer_select = ''

def get_computer_selection():
  global computer_select
  print("\n Computer turn.......")

  #We make a specific interval that the computer choose a random  number between (1,3)
  computer_choice = random.randint(1, 3)

  # It is okay if the computer makes the same choice

  if computer_choice == 1:
    computer_select = 'rock'
  elif computer_choice == 2:
    computer_select = 'paper'
  else:
     computer_select= 'scissor'
```

This way, we can call the function `get_computer_selection()` whenever the computer has to play the turn.

```python
get_computer_selection()
print("Computer has selected: " + computer_select)
```

We can also make functions that increase the score of the player or the computer. For this example we will make a function to increase the score of the player.

Code snippet:
```python
# initialize score
player_score = 0

def player_win_round():
  global player_score
  player_score += 1
```

This way, the player score is incremented by one when the player wins the round.

Last but not least, since we are keeping track of the score, we should also ask the player the amount of points to win the game. We can prompt this input at the beginning of the game.

Code snippet:
```python
# initialize points to win
points_to_win = 0

print("Enter the amount of points to win.")
# take the input from the user for the amount of points to win
points_to_win = int(input("Points to win: "))
```

We can then use a while loop to make the player play the game until either the player or the computer reaches the amount of points to win.

Code snippet:
```python
while player_score < points_to_win and computer_score < points_to_win:
  # play the game
```

We also have to do the condition handling on who wins the round by comparing the choice of the player and the computer. We can do something like this for example.

Code snippet:
```python
if player_select == computer_select:
  print(player_select.capitalize() + " Vs " + computer_select.capitalize() + ", It's a draw!")
if player_select == 'paper' and computer_select == 'rock':
  print(player_select.capitalize() + " Vs " + computer_select.capitalize() + ", Player wins the round!")
```

Now that we have all the pieces needed, we are going to combine them with what we have from week 4 and finally make a complete Rock, Paper, Scissors game!

Code snippet for this week:

```python
# import random module
import random

#variable initialization
points_to_win = 0
player_score = 0
computer_score = 0
player_select = ''
computer_select = ''

# function if player wins round
def player_win_round():
  global player_score
  player_score += 1
  print(player_select.capitalize() + " Vs " + computer_select.capitalize() + ", Player wins the round!")

# function if computer wins round
def computer_win_round():
  global computer_score
  computer_score += 1
  print(player_select.capitalize() + " Vs " + computer_select.capitalize() + ", Computer wins the round!")

# function for the computer selection
def get_computer_selection():
  global computer_select

  print("\nComputer's turn.......")

  #We make a specific interval that the computer choose a random  number between (1,3)
  computer_choice = random.randint(1, 3)

  # It is okay if the computer makes the same choice

  if computer_choice == 1:
    computer_select = 'rock'
  elif computer_choice == 2:
    computer_select = 'paper'
  else:
     computer_select= 'scissors'

  print("Computer has selected: " + computer_select.capitalize())

def get_player_selection():
  global player_select
  print("\nEnter your choice: \n 1 for Rock \n 2 for Paper \n 3 for Scissors \n")
 
 	# take the input from the user for making a selection
  player_choice = int(input("Player's turn: "))
 
 #looping until user enter invalid input
  while player_choice > 3 or player_choice < 1:
     player_choice = int(input("Your input is not valid, please enter a value between 1,3: "))
		
  if player_choice == 1:
    player_select = 'rock'
  elif player_choice == 2:
    player_select = 'paper'
  else:
    player_select = 'scissors'

  # print user choice
  print("The player has selected: " + player_select.capitalize())


# display message
print("Welcome to the game of Rock Paper Scissors.")

print("Enter the amount of points to win.")
# take the input from the user for the amount of points to win
points_to_win = int(input("Points to win: "))

#runs the loop as long as the player points or computer 
while player_score < points_to_win and computer_score < points_to_win:
	
  get_player_selection()
  get_computer_selection()

  if player_select == computer_select:
    print(player_select.capitalize() + " Vs " + computer_select.capitalize() + ", It's a draw!")
  elif player_select == 'paper' and computer_select == 'rock':
    player_win_round()
  elif player_select == 'rock' and computer_select == 'scissors':
    player_win_round()
  elif player_select == 'scissors' and computer_select == 'paper':
    player_win_round()
  else:
    computer_win_round()

  print("\nThe score is " + str(player_score) + " to " + str(computer_score))

if player_score == points_to_win:
  print("\nPlayer wins the game!")
else:
  print("\nComputer wins the game!")

```

And that ladies and gentlemen, we have coded our first game of "Rock, Paper, Scissors". Of course, this does not mean that this is the end. Feel free to change and put your personal touch to make it your own. Good luck!
