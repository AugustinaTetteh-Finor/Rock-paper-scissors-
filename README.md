# Rock-paper-scissors-
import random

def player(prev_play, opponent_history=[]):
    # Keep track of the opponent's last move
    if prev_play:
        opponent_history.append(prev_play)

    # If this is the first move, choose randomly
    if not opponent_history:
        return random.choice(["R", "P", "S"])

    # Analyze the opponent's last move
    last_move = opponent_history[-1]

    # Simple strategy: counter the opponent's last move
    if last_move == "R":
        return "P"  # Paper beats Rock
    elif last_move == "P":
        return "S"  # Scissors beats Paper
    elif last_move == "S":
        return "R"  # Rock beats Scissors

    # In case of an unexpected input, choose randomly
    return random.choice(["R", "P", "S"])
    
