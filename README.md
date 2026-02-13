#  Tambola (Housie) Game Simulation – Detailed Description

This Tambola (Housie) game simulation is a console-based Python project that demonstrates the practical use of core programming concepts such as functions, loops, dictionaries, lists, conditional statements, exception handling, and the built-in `random` module. The game begins by initializing a game board containing numbers from 1 to 20, which are shuffled randomly using `random.shuffle()` to ensure fairness and unpredictability in number calling. The program then asks the user to enter the number of players, and it includes error handling using `try-except` to manage invalid inputs or negative values by assigning default player counts when necessary.

For each player, a ticket is generated using `random.sample()`, ensuring that every ticket contains 5 unique numbers selected randomly from the same 1–20 range. These ticket numbers are sorted for better readability and stored in a dictionary where player names act as keys and their tickets as values. Another dictionary is used to track the number of matches for each player during the game.

The game simulation starts by iterating through the shuffled game board, calling one number at a time. Each called number is stored in a list to maintain a record of all announced numbers. The program checks whether the called number exists in any player's ticket and updates their match count accordingly. Whenever a match is found, the program prints a progress update showing how many numbers the player has matched out of 5.

The winning condition is simple and clear: when a player's match count reaches 5, they are added to the winners list. The game immediately stops after announcing the winner(s), displaying their name(s), winning ticket(s), the final number called, and the total number of numbers announced during the game.

This project effectively simulates the core mechanics of Tambola in a simplified format (1–20 instead of 1–90) and is ideal for beginners to understand logic building, game flow control, and structured programming in Python.
