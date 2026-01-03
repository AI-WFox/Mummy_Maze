# Mê Cung Tây Du - MAZE GAME

## Overview
Mê Cung Tây Du is a strategic 2D maze puzzle game inspired by the legendary Journey to the West. Developed with C++23 and the SDL3 library, the game challenges players to guide Sun Wukong through ancient labyrinths, reaching the exit portal while outsmarting various monsters.

## My Core Contributions
As a primary developer for this project, I implemented the following critical systems and logic:

### Intelligent Monster AI (Hard Mode)
Developed a sophisticated AI system for the Hard difficulty level using a Finite State Machine (FSM).
- Hunt State: Direct pursuit using BFS (Breadth-First Search) pathfinding.
- Search State: Systematic spiral search around the last known player position.
- Intercept State: Uses a predictive model to calculate the player's future trajectory and tactical waypoints to cut off their path to the exit.
- Patrol State: Strategic area coverage between the map center and the exit portal.

### Advanced State Management
Implemented a comprehensive game state persistence system for seamless gameplay.
- Undo/Redo/Reset: Built a robust system using Stack data structures to capture and restore GameStateSnapshots.
- Snapshot Architecture: Captures entity coordinates, turn history, and even internal AI states to ensure deterministic state restoration.

### Dynamic Map System
Engineered the backend logic for maze environments.
- Grid Parser: Developed a flexible parser that loads level data from text files.
- Semantic Mapping: Implemented tile-based logic for walls, entity spawns, and exit triggers.

### Core Gameplay Mechanics
- Turn-based System: Developed the logic where monsters move twice for every player move.
- Optimization: Refined pathfinding performance and resolved critical collision detection bugs.

## Technical Stack
- Language: C++23
- Graphics Library: SDL3
- Extension Libraries: SDL3_image, SDL3_ttf
- Algorithms: BFS Pathfinding, Finite State Machine (FSM), Linear Prediction

## Gameplay Mechanics
- Movement: Navigate using Arrow keys.
- Difficulty Scaling: The game scales from basic probabilistic pursuit to highly tactical predictive interception.
- Victory Condition: Reach the exit tile without colliding with enemy entities.

## Installation and Build
### Requirements
- GCC compiler supporting C++23
- SDL3, SDL3_image, SDL3_ttf libraries
- Windows OS

### Build Instructions
1. PowerShell Method:
   ```powershell
   g++ -std=c++23 -O2 -Wall -Ilibs/include -Llibs/lib (Get-ChildItem src -Recurse -Filter *.cpp).FullName -lSDL3 -lSDL3_image -lSDL3_ttf -o build\mummymaze.exe; ./build\mummymaze.exe
   
   ```

2. Automated Script:
   Execute the build.vbs file to initiate the compilation and startup process.

## Project Architecture
- src/ai/: Logic for pathfinding and behavior state machines.
- src/entities/: Classes for player and monster attributes.
- src/ingame/: Map loaders and core gameplay loop management.
- assets/: Visual and audio resources.
- libs/: External dependencies and header files.
