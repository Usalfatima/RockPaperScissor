# RockPaperScissor


import random

def player(prev_play, opponent_history=[]):
    """
    Bot implementation for playing Rock, Paper, Scissors.
    """
    if not prev_play:
        # Play a random move for the first game
        return random.choice(['R', 'P', 'S'])
    
    # Define a dictionary to keep track of the frequencies of opponent's moves
    move_frequencies = {'R': 0, 'P': 0, 'S': 0}
    for move in opponent_history:
        move_frequencies[move] += 1
    
    # Determine the move that beats the most frequent move played by the opponent
    most_frequent_move = max(move_frequencies, key=move_frequencies.get)
    if most_frequent_move == 'R':
        return 'P'
    elif most_frequent_move == 'P':
        return 'S'
    else:
        return 'R'

from RPS_game import play, player, quincy, abbey, kris, mrugesh

# Play 1000 games against each bot and print the results
play(player, quincy, 1000, verbose=True)
play(player, abbey, 1000, verbose=True)
play(player, kris, 1000, verbose=True)
play(player, mrugesh, 1000, verbose=True)
