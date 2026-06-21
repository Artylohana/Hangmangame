# Hangmangame
words = ["apple", "mango", "grape", "peach"]

for word in words:

    guessed = ""
    turns = 6

    print("\nNew Word")

    while turns > 0:

        failed = 0

        for letter in word:
            if letter in guessed:
                print(letter, end=" ")
            else:
                print("_", end=" ")
                failed += 1

        print()

        if failed == 0:
            print("You Win!")
            break

        guess = input("Enter a letter: ").lower()

        guessed += guess

        if guess not in word:
            turns -= 1
            print("Wrong Guess")
            print("Turns left:", turns)

    if turns == 0:
        print("Game Over")
        print("The word was:", word)

print("\nAll words completed!")
