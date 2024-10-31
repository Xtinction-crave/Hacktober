# Cat and Mouse Game

In this game, you are a **cat** represented by two adjacent cells labeled "X" (one for the head, one for the tail) on a **6x6 grid**. Your objective is to catch all **5 mice** on the grid. The mice move randomly, while you control the cat using directional commands.

**Winning Condition**: Catch all mice within 20 moves.

**Losing Condition**: Fail to catch all mice within 20 moves.

---

## Task Breakdown

### **Task 1.1: Setting Up the Game Grid with Cat and Mouse**

Write a function `initialize_grid()` to set up the initial 6 by 6 game grid.

- The grid should be represented as a 2D list, with empty spaces filled by a placeholder (`"_"`).
- Place the cat's head (`"H"`) and tail (`"T"`) on two adjacent cells at the top left hand corner of the grid.
- Place the 5 mice (`"M"`) randomly on the grid, ensuring they don’t overlap with each other or the cat.

**Example Output**:
```python
[['H', 'T', '_', 'M', '_', '_'],
 ['_', '_', '_', '_', 'M', '_'],
 ['_', 'M', '_', '_', '_', '_'],
 ['_', '_', '_', '_', '_', '_'],
 ['M', '_', '_', '_', '_', 'M'],
 ['_', '_', '_', '_', '_', '_']]

```

---

### **Task 2: Moving the Cat**

Write a function `move_cat(direction)` to control the cat's movement based on user input.

- Accept one of four directions: "up", "down", "left", or "right".
- Move the cat’s head and tail in the chosen direction, ensuring they stay adjacent.
- Prevent the cat from moving outside the grid boundaries.
- Update the grid to reflect the new positions of the cat’s head and tail.

**Example**:
```python
move_cat("up")  # Moves the cat up by one cell
```

---

### **Task 3: Moving the Mice**

Write a function `move_mice()` that moves each mouse randomly by one tile per turn.

- For each mouse, choose a random adjacent cell (up, down, left, right) to move into.
- Ensure mice don’t move outside the grid or onto other mice.
- If a mouse moves into the cat’s head, the mouse is "caught" and removed from the grid.

---

### **Task 4: Checking for Wins and Losses**

Write a function `check_game_status(moves_left, mice_left)` to evaluate the game's win/loss conditions.

- **Win**: Return `True` if all mice have been caught (i.e., `mice_left == 0`).
- **Loss**: Return `True` if `moves_left` reaches 0 and there are still mice on the grid.
- Display an appropriate win/loss message based on the game outcome.

**Example**:
```python
if check_game_status(moves_left, mice_left):
    print("Congratulations, you won!")
else:
    print("Game Over. You ran out of moves.")
```

---

### **Task 5: Game Loop and User Input**

Write the main game loop to:
- Display the grid after each turn.
- Accept user input for the cat’s movement.
- Update the cat’s and mice’s positions based on user input and random movements, respectively.
- Track the number of moves left.
- End the game if a win or loss condition is met.


