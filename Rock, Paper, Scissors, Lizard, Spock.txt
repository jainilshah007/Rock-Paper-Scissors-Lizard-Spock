import random

def play():
    user = input("What's your choice? 'r' for rock, 'p' for paper, 's' for scissors, 's' for spock, 'l' for lizard\n")
    
    computer = random.choice(['r', 'p', 's','l','sp'])

    if user == computer:
        return 'It\'s a tie'

    # r > s, s > p, p > r, r > l , l > sp , sp > s , s > l , l > p , p > sp , sp > r ,r>s
    print(computer)
    if is_win(user, computer):
        
        return 'You won!'

    return 'You lost!'

def is_win(player, opponent):
    # return true if player wins
    # r > s, s > p, p > r
    if (player == 'r' and opponent == 's') or (player == 's' and opponent == 'p') \
        or (player == 'p' and opponent == 'r') or (player == 'r' and opponent == 'l') or \
        (player == 'l' and opponent == 'sp') or (player == 'sp' and opponent == 's') or \
        (player == 's' and opponent == 'l') or (player == 'l' and opponent == 'p') or \
        (player == 'p' and opponent == 'sp') or\
        (player == 'sp' and opponent == 'r') or (player == 'r' and opponent == 's'):
        return True
print(play())