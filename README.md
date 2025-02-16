# Hamgman-Game
# from this stages the user know that how many chance are remain 
stages = ['''
    +---+
    |   |
    0   |
    /|\ |
    / \ |
===========   
''', '''
    +---+
    |   |
    0   |
   /|\  |
   /    |
        |
===========
''', '''
   +---+
   |   |
   0   |
  /|\  |
       |
       |
==========
''', '''
   +---+
   |   |
   0   |
  /|   |
       |
       |
==========
''', '''
   +---+
   |   |
   0   |
   |   |
       |
       |
==========
''', '''
   +---+
   |   |
   0   |
       |
       |
       |
===========
''', '''
   +---+
   |   |
       |
       |
       |
       |
''']

import random

# Removed the unnecessary import statement
word_list = ["apple", "beautiful", "potato"] # we can add many names
lives = 6
chosen_word = random.choice(word_list)
print(chosen_word)
display = []
for letter in range(len(chosen_word)):
    display.append('_')
print(display)
game_over = False
while not game_over:
    guessed_letter = input("Guess a letter: ").lower()
    for position in range(len(chosen_word)): # for generating the range
        letter = chosen_word[position]
        if letter == guessed_letter:
            display[position] = guessed_letter
            print(display)
    if guessed_letter not in chosen_word:
        lives -= 1
        if lives == 0:
            game_over = True
            print("You Lose!!")

    if '_' not in display:
        game_over = True
        print("You Win!!")
    print(stages[lives])

