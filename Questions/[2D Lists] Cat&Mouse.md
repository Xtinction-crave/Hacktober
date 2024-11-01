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
[['T', 'H', '_', 'M', '_', '_'],
 ['_', '_', '_', '_', 'M', '_'],
 ['_', 'M', '_', '_', '_', '_'],
 ['_', '_', '_', '_', '_', '_'],
 ['M', '_', '_', '_', '_', 'M'],
 ['_', '_', '_', '_', '_', '_']]

```

---

### **Task 1.2: Moving the Cat**

The cat is special with its head and tail moving separately.

Write a function `move_cat(grid, head_pos, tail_pos, direction)`, where head_pos is (x, y) coordinates of the cat's head, and 'move_cat_tail(grid, head_pos, tail_pos, direction)' control the cat's movement based on user input.

- The direction would accept these criteria: "up", "down", "left", "right", "ldu"(left diagonal upwards), "rdu"(right diagonal upwards), "ldd"(left diagonal downwards), "rdd"(right diagonal downwards)
- Move the cat’s head and the tail in the chosen direction
- Move the tail in a box grid around the head, ensuring they stay adjacent.This does not count as a move and is optional to the user.
- Prevent the cat (head or tail) from moving outside the grid boundaries.
- If the cat head is going out,it would remain at its position, tail would still move in that direction if possible.
- Update the grid to reflect the new positions of the cat’s head and tail.

**Example**:
```python
move_cat("down")  # Moves the cat down by one cell
move_cat_tail("up") # Moves the tail up by one cell
```

Write another function where the position of the head or tail is swapped. This takes up 1 move too.

---

### **Task 1.3: Moving the Mice**

Write a function `move_mice()` that moves each mouse randomly by one tile per turn.

- For each mouse, choose a random adjacent cell (up, down, left, right) to move into.
- Ensure mice don’t move outside the grid, onto other mice or the cat's tail.
- If a mouse moves into the cat’s head, the mouse is "caught" and removed from the grid.

---

### **Task 1.4: Checking for Wins and Losses**

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

### **Task 1.5: Game Loop and User Input**

Write the main game loop to:
- Display the grid after each input by user replacing the (`","`) with (`"|"`). Don't show the list brackets too.
- Accept user input for the cat’s movements.
- Ask them whether they want to move the tail then ask whether they want to turn around(swap head and tail position), and act accordingly.
- Update the cat’s and mice’s positions based on user input and random movements, respectively.
- Track the number of moves left, showing it to the user.
- End the game if a win or loss condition is met.
