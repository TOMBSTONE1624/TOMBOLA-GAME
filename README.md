# TOMBOLA-GAME
import random
game_board = list(range(1, 21))
random.shuffle(game_board)
called_numbers = []

print(f"Game Board Initialized and Shuffled: {game_board}")

def generate_tickets(num_players):
    player_tickets = {}
    for i in range(1, num_players + 1):
        ticket = random.sample(range(1, 21), 5)
        player_tickets[f"Player {i}"] = sorted(ticket)
    return player_tickets

try:
    num_test_players = int(input("Enter the number of players: "))
    if num_test_players < 1:
        print("Please enter at least 1 player. Defaulting to 1.")
        num_test_players = 1
except ValueError:
    print("Invalid input. Defaulting to 3 players.")
    num_test_players = 3

tickets = generate_tickets(num_test_players)

print(f"\nGenerated tickets for {num_test_players} players:")
for player, ticket in tickets.items():
    print(f"{player}: {ticket}")

player_matches = {player: 0 for player in tickets}
winners = []

print("\n--- Starting Tambola Game Simulation ---")

for called_num in game_board:
    called_numbers.append(called_num)
    print(f"\nHost calls: {called_num}")
    for player, ticket_nums in tickets.items():
        if called_num in ticket_nums:
            player_matches[player] += 1
            print(f"-> Match found for {player}! (Total: {player_matches[player]}/5)")
            if player_matches[player] == 5:
                winners.append(player)
    if winners:
        print("\n*** GAME OVER ***")
        for winner in winners:
            print(f"Winner: {winner}")
            print(f"Winning Ticket: {tickets[winner]}")
        print(f"Final number called: {called_num}")
        print(f"Total numbers called: {len(called_numbers)}")
        break
