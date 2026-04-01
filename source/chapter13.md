# Chapter 13: Practice Projects

This section of the basic Python course is intended for you to practice what you have learned so far. There is a lot you can do with what you already know, and in this short article you are getting a couple of ideas for practice projects. Let's get started and have fun!

## Rock, paper, scissors game

This is a two player game where each of them randomly chooses between rock, paper or scissors. In this case you can make a user play against the computer. You can read more about this popular game in the [wikipedia article](https://en.wikipedia.org/wiki/Rock_paper_scissors). The basic rules are:

- Rock beats scissors
- Paper beats rock
- Scissors beats paper

The Python program can work like the following after executing the script:

```
Game number 1
Rock (R), paper (P) or scissors (S)? (Q to quit): R
You have chosen Rock, while the computer chose Paper
You lost

Game number 2
Rock (R), paper (P) or scissors (S)? (Q to quit): p
You have chosen Paper, while the computer chose Rock
You won!

Game number 3
Rock (R), paper (P) or scissors (S)? (Q to quit): S
You have chosen Scissors, while the computer chose Rock
You lost

Game number 4
Rock (R), paper (P) or scissors (S)? (Q to quit): T
Incorrect input. Please try again.

Game number 4
Rock (R), paper (P) or scissors (S)? (Q to quit): r
You have chosen Rock, while the computer chose Scissors
You won!

Game number 5
Rock (R), paper (P) or scissors (S)? (Q to quit): r
You have chosen Rock, while the computer chose Scissors
You won!

Game number 6
Rock (R), paper (P) or scissors (S)? (Q to quit): P
You have chosen Paper, while the computer chose Scissors
You lost

Game number 7
Rock (R), paper (P) or scissors (S)? (Q to quit): q
Thank you for playing!
You won 3 out of 6 games (50.00%)
```

The user plays against the computer one game after another as long as the user doesn't choose the option to quit, which can be the letter Q. Here is a list of things to consider for the Python script:

1. In order to play games indefinitely until a condition is met (choosing Q to quit) you can make use of a `while` loop. There are a couple of ways to do it, but one popular way to make an infinite loop is by using the `while True`. Keep in mind that if you don't use a proper ending condition in the loop, you may end up with an infinite loop.
2. The program needs to prompts the player (you) for either rock, paper or scissors. Remember you can use the `input()` function for this.
3. The computer also needs to choose between rock, paper or scissors. You could make use of the `random` module to randomly choose between the three options, particularly with the `choice()` function.
4. In each game you need to check who won, or if there was a tie. For this you could make a series of `if-else` and possibly `elif` statements. For example, if the user chooses Rock and the computer chooses Scissors, then the user won the game.
5. You could keep a score of the game by using a variable `score`, initially being equal to 0. Each game you win adds up one point to the final score. Remember you can increase a variable with `score = score + 1` or `score += 1`.

## Countdown timer and clock

In this simple project the idea is to prompt the user for a number of seconds and show a countdown timer with minutes and seconds. The total number of seconds will be an integer number.

After running the script you should be looking at something like this:

```
Enter the time in seconds: 62
You have entered 62 seconds
01:02
01:01
01:00
00:59
00:58
00:57
...
00:03
00:02
00:01
00:00
Time's up!
```

First, you can print a message showing the number of seconds the user just entered. This can sound silly for a small and simple program like this one, but it is a good idea for larger projects to show the user what the inputs are as a way to confirm.

Then the countdown begins. In the example above the user entered 62 seconds. That means that the time can be split in 1 minute and 2 seconds. Then, the first line should be something like `01:02` which is the standard format in which a digital clock shows the time.

As the time passes, the number of seconds decreases by one, and when the seconds reach zero the number of minutes decreases, at which point the seconds go all the way up to 59.

The program stops when the total number of seconds reaches zero. Then you can show a message indicating that the time is up.

A couple of things to consider when you work on this small project:

1. Use the `input()` function to prompt the user for the total number of seconds. Remember what is the data type that the `input()` function returns? The `input()` function has been covered in the [functions chapter](chapter10) of this course. You will need to convert this to an integer number for later use.
2. If you need to compute the number of minutes and seconds from the total number of seconds, you could make use of the integer division and modulus operators. These topics were covered in the [terminal and python interpreter](chapter2) article.
3. You learned about Python modules in a [previous article](chapter12) from this course. There is a module called [time](https://docs.python.org/3/library/time.html) which you can use in this project to wait for one second between each pass. Specifically, look for the [sleep()](https://docs.python.org/3/library/time.html#time.sleep) method of this module.