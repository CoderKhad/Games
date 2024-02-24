# Tic-tac-toe-game

# Tic-Tac-Toe Game

# Initializing the game board
board = [' '],[' '],[' '],
		[' '],[' '],[' '],
		[' '],[' '],[' ']

# Game loop
while True:
	# Getting user input
	move = input('Enter a number (1-9): ')
	
	# Validating user input
	if move in ['1', '2', '3', '4', '5', '6', '7', '8', '9']:
		move = int(move)
	else:
		print('Invalid input!')
		continue
	
	# Checking if the space is already occupied
	if board[move-1] != ' ':
		print('Space already occupied!')
		continue
	
	# Marking the space with X or O
	board[move-1] = 'X' if player == 'X' else 'O'
	
	# Printing the updated board
	print(board)
	
	# Checking for wins or draws
	if (board[0] == board[1] == board[2] or board[3] == board[4] == board[5] or board[6] == board[7] == board[8]) or (board[0] == board[3] == board[6] or board[1] == board[4] == board[7] or board[2] == board[5] == board[8]):
		print('Game over!')
		break
	elif all(' ' not in board for i in range(9)):
		print('Draw!')
		break
	
	# Switching players
	player = 'X' if player == 'O' else 'O'
