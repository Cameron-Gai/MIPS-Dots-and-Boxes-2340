# Dots & Boxes Game in MIPS Assembly

## Project Description

This repository contains an implementation of the classic **Dots & Boxes** game in **MIPS Assembly**. The game allows a human player (`P`) to compete against a computer AI (`C`) on a configurable dot grid. Players take turns drawing lines between adjacent dots, forming boxes to score points and earn extra turns. The assembly program demonstrates low-level programming concepts, including memory management, register usage, system calls, and modular design across multiple `.asm` files.

## Features

* **Interactive Gameplay**: Prompt-based user input for row and column selection, with validation to prevent illegal or repeated moves.
* **AI Opponent**: Simple pseudo-random move generator with the same validation logic as the human player.
* **Box Detection**: Six-case switch logic to detect completed boxes and award points, including extra turns for box creation.
* **Score Tracking**: Real-time display of user and AI scores, with final winner announcement.
* **ASCII Board Rendering**: Efficient 1D memory array representation of a 2D board, displayed with dots (`+`), horizontal (`-`) and vertical (`|`) lines.
* **Sound Effects**: Syscall-based audio feedback on moves and scoring events.
* **Modular Design**: Separate Assembly modules for board management, gameplay control, box checking, and the main driver.

## Architecture

The project is organized into four core `.asm` modules plus auxiliary resources:

* **`board_manager.asm`**: Initializes and displays the 2D game board using a 1D memory buffer and ASCII characters.
* **`gameplay_manager.asm`**: Handles user input, AI move generation, input history tracking, score display, and turn counting.
* **`box_checker.asm`**: Implements the six-case detection logic for completed boxes for both player and AI, updates scores, and triggers sound effects.
* **`main.asm`**: Orchestrates the game loop by invoking initialization, display, input, box checking, and game-state routines.

Additional documentation:

* **`Report.pdf`**: Detailed project report covering abstract, challenges, algorithms, and peer evaluation.
* **`Dots__Boxes_User_Manual.pdf`**: User manual with setup instructions, gameplay overview, and sample screenshots.
* **Video Demonstration**: [Watch on YouTube](https://www.youtube.com/watch?v=WP74JU8sLl4).

## Prerequisites

* **MARS** or **SPIM** MIPS Simulator (tested on MARS 4.5).
* Java Runtime Environment for MARS if using the JAR.
* Basic familiarity with MIPS syscalls and assembly instructions.

## Installation & Assembly

1. Clone this repository:

   ```bash
   git clone https://github.com/<username>/dots-and-boxes-mips.git
   cd dots-and-boxes-mips
   ```
2. Open MARS (e.g., `Mars4_5.jar`) with the "Assemble all files in directory" option enabled.
3. Assemble and run **`main.asm`**.

## Usage

* Upon launch, the program displays an empty 13×17 ASCII grid (representing a 6×8 game board).
* Enter the **row** and **column** indices to draw a line between dots (bounds: row 0–12, column 0–16).
* The program prevents illegal moves (out-of-bounds, repeated, or non-adjacent placements).
* Complete a box to score a point and earn an extra turn. Boxes are marked with `P` (player) or `C` (computer).
* The game ends when no further moves are available. The higher score wins, or a tie is declared.

## Challenges & Learning

* **Register Management**: Overcame limited MIPS registers by using `.word` memory storage and disciplined register usage.
* **Modular Assembly**: Learned to structure multi-file assembly projects and manage symbol visibility across modules.
* **Board Representation**: Developed an efficient 1D array approach to model a 2D ASCII board, simplifying display and logic.
* **Box Recognition**: Implemented a 12-case switch mechanism (six for player, six for AI) using relative offsets.
* **User Input Validation**: Built robust checks for non-numeric, out-of-bounds, odd/even parity, and repeated moves.
* **Syscall Audio**: Explored MIPS Syscall 31 for playing tones, enhancing user feedback.

## Authors

* **Cameron Gai** (chg200002)
* **Christopher Chaiban** (csc210003)
* **Edwin Feng** (exf210015)
* **Sayed Rahman** (smr210001)

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
