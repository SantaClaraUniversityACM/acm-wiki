```python
import random


def check_guess(guess, number_to_guess):
    # Check if the guess is correct, too low, or too high
    if guess < number_to_guess:
        print("Too low! Try again.")
    elif guess > number_to_guess:
        print("Too high! Try again.")
    else:
        return True
    return False


def number_guessing_game():
    # Use the random library to generate a random number between 1 and 100
    number_to_guess = random.randint(1, 100)
    attempts = 0
    guessed = False

    print("Welcome to the Number Guessing Game!")
    print("I have selected a number between 1 and 100. Try to guess it!")

    # Keep asking the user to guess the number until they get it right
    while not guessed:
        # Use a try-except block to handle invalid input
        try:
            # Get the user's guess
            guess = int(input("Enter your guess: "))
            attempts += 1

            correct = check_guess(guess, number_to_guess)
            if correct == True:
                guessed = True
            else:
                continue
        except ValueError:
            print("Invalid input. Please enter a valid number.")

    return attempts


# Run the number guessing game when file is executed
if __name__ == "__main__":
    attempts = number_guessing_game()
    print(f"Congratulations! You guessed the number in {attempts} attempts.")
```
