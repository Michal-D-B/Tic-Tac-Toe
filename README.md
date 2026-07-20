# Tic Tac Toe ⭕ ❌

A command-line Tic Tac Toe game for two players, written in Python. Take turns on a 3×3 grid, and the first player to line up three of their marks — horizontally, vertically, or diagonally — wins. If the board fills up with no winner, it's a draw.

## Features

- **Two-player local play** — players take turns on the same keyboard.
- **Choose your mark** — Player 1 picks X or O; Player 2 gets the other.
- **Numpad-style board** — squares are selected with numbers 1–9, laid out to match a keyboard numpad (7-8-9 across the top).
- **Clean grid display** — the board is drawn with proper row and column separators.
- **Full input validation** — the game re-prompts on invalid input and won't let you pick a taken square.
- **Win and draw detection** — all rows, columns, and both diagonals are checked; a full board ends in a draw.
- **Replay loop** — play as many games as you like without restarting.

## How to Play

1. Run the program.
2. Player 1 chooses to be **X** or **O**.
3. Confirm you're ready to play.
4. On your turn, enter a number from **1–9** to place your mark:

   ```
    7 | 8 | 9
   ---+---+---
    4 | 5 | 6
   ---+---+---
    1 | 2 | 3
   ```

5. The board updates after every move.
6. Get three in a row to win — or fill the board for a draw.
7. Choose whether to play again.

## Requirements

- Python 3.x
- Runs best in **Jupyter Notebook** (uses `IPython.display.clear_output` to refresh the board between moves).

## Running the Game

Open `Tic_Tac_Toe_Final.ipynb` in Jupyter Notebook and run the cell.

## How It Works

The game is organised into small, single-purpose functions:

| Function | Responsibility |
|----------|---------------|
| `main()` | Runs the overall flow: setup, turn loop, and replay. |
| `player_choice()` | Lets Player 1 pick X or O and assigns Player 2 the other. |
| `player_order()` | Decides who moves first based on the chosen mark. |
| `player_ready()` | Confirms the players are ready to start. |
| `player_number_choice()` | Gets a valid, unused square from the current player. |
| `display_game()` | Draws the board grid. |
| `game_score()` | Checks all rows, columns, and diagonals for a winner. |
| `draw()` | Detects a full board with no winner. |
| `replay()` | Asks whether to play another game. |

### Board Coordinate Mapping

Each numbered square maps to a `(row, index)` location inside the board dictionary:

```python
dic_choice = {
    '1':('row3',0), '2':('row3',1), '3':('row3',2),
    '4':('row2',0), '5':('row2',1), '6':('row2',2),
    '7':('row1',0), '8':('row1',1), '9':('row1',2)
}
```

When a player enters a number, the game looks up its location and updates that exact cell — a clean way to translate simple input into a position on the board.

### Turn Handling

A single move-handling block serves whichever player's turn it is, then flips the turn with:

```python
p_order = not p_order
```

## Possible Improvements

- Add a computer opponent (a random-move AI, or an unbeatable minimax version).
- Track wins across multiple games with a running scoreboard.
- Add player names and a colored board.
