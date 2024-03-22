import random

def player(prev_play, opponent_history=[]):
    if prev_play:
        opponent_history.append(prev_play)

    # Implement your strategy here
    if len(opponent_history) < 10:
        return random.choice(['R', 'P', 'S'])
    else:
        # Analyze opponent's history and make a decision based on it
        # For example, you can look for patterns or try to predict their next move
        return predict_next_move(opponent_history)

def predict_next_move(opponent_history):
    # Implement your prediction logic here
    # For simplicity, let's just return the opposite move of the opponent's last move
    last_move = opponent_history[-1]
    if last_move == 'R':
        return 'P'
    elif last_move == 'P':
        return 'S'
    else:
        return 'R'
