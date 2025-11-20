

# **Scrabble Game in C**

This project is a **console-based Scrabble game** implemented in C.
It supports two players, tile generation, scoring, word validation, and a complete game board with special score tiles such as **Double Letter**, **Triple Letter**, **Double Word**, and **Triple Word**.

The game uses:

* **Binary Search Tree (BST)** for storing already-used words
* **Linked list** for storing the tile bag
* **Random tile generation**
* **Word validation** using dictionary file
* **Scrabble-style scoring**

---

## **📌 Features**

### ✔️ Scrabble Board (15×15)

* Fully rendered board with

  * Triple Word (`+3`)
  * Double Word (`+2`)
  * Triple Letter (`*3`)
  * Double Letter (`*2`)
* Letters placed on board persist and interact with new placements.

### ✔️ Tile Bag

* Loaded from `letters1.csv`
* Each tile has:

  * letter
  * index
  * count
  * score

### ✔️ Player Racks

* Each player gets **10 tiles**.
* When a word is successfully formed, tiles used are replaced with new random tiles.

### ✔️ Word Validation

* Every word is checked using:

  * **`words2.txt` dictionary file`**
  * **`search_tree()`** to prevent duplicate words
  * Board adjacency rules (connecting to other words)

### ✔️ Scoring System

* Uses Scrabble-style scoring for each letter.
* Applies:

  * **Letter multipliers**
  * **Word multipliers**
* Automatically tracks **Player 1** and **Player 2** scores.

### ✔️ Horizontal and Vertical Word Placement

* User inputs:

  ```
  row,column
  H/V
  word
  ```
* Program validates:

  * Available tiles
  * Board boundaries
  * Existing board letters
  * Dictionary validity

---

## **📁 Required Files**

Your project requires the following additional files:

### ✔️ `letters1.csv`

Contains tile information:

```
index,letter,count,score
```

### ✔️ `words2.txt`

A dictionary file containing acceptable English words:

```
APPLE
CAT
PROGRAM
...
```

---

## **🛠️ How to Compile & Run**

### **Compile**

```bash
gcc scrabble.c -o scrabble
```

If you are on Windows and using `conio.h`, compile with MinGW or Turbo C compiler.

### **Run**

```bash
./scrabble
```

---

## **📌 Game Flow**

1. Program initializes board and tile bag
2. Player 1 and Player 2 each receive 10 random tiles
3. Players take turns entering:

   * coordinates
   * direction
   * word
4. Program:

   * Validates the move
   * Calculates score
   * Places letters on board
   * Replaces used tiles
5. Game switches to next player
6. Continues until tiles are exhausted or game is manually stopped

---

## **📚 Data Structures Used**

### ✔️ **Binary Search Tree**

Used to store already-played words to prevent duplicates.

### ✔️ **Linked List**

Used for tile bag storage.

### ✔️ **4-Dimensional Array**

Represents the Scrabble board:
`board[15][15][5][7]`

Stores borders and tile information.

---

## **📸 Sample Output**

```
PLAYER 1:
Enter row/colm (example: 12,12)
Horizontal or Vertical (H/V)
Enter the word:
tiles used = 10
player1 score: 34
player2 score: 18
```

