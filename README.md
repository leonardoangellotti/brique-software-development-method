# BRIQUE GAME  
Implementation of *Brique* by Luis Bolaños Mures  
Developed by Alessio Valle and Leonardo Angellotti

## Introduction

This repository contains a Java implementation of the board game **Brique**, originally created by Luis Bolaños Mures.

The project was developed with a strong focus on software engineering principles and clean architecture, aiming to reproduce the game while following good software development practices such as modularity, extensibility, separation of concerns, and maintainability.

---

## Installation

The latest stable version is available in the Releases section.  
You can run the project in three different ways.

### Run the JAR File

Download the `.jar` file and double-click it, or run it from the terminal:

```bash
java -jar <PATH-TO-FILE>
```

This launches the graphical version of the game.

To start the CLI version instead:

```bash
java -jar <PATH-TO-FILE> CLI
```

---

### Run from ZIP / TAR Archive

The archive contains a `bin/` directory with scripts for launching the application directly.

---

### Compile from Source

Clone the repository and run the following command from the project root:

```bash
./gradlew clean build
```

After compilation, run the CLI version with:

```bash
java -cp build/classes/java/main brique.Main CLI
```

---

# Project Structure

## Packages

### `brique.core`

Contains the core game logic and engine classes.

Main components:

- **GameEngine**  
  Facade interface used to interact with the game.  
  It allows selecting different game modes and processes moves according to the active ruleset.

- **GameState**  
  Represents the current state of the game and is updated by the engine during gameplay.

---

### `brique.exceptions`

Contains custom exceptions used to handle errors and invalid operations during the game loop.

---

### `brique.rules`

Contains the game rules implementation and supports future extensibility for additional rulesets.

Main components:

- **StandardBriqueRules**  
  Processes player moves according to the standard Brique rules.

- **RulesFactory**  
  Factory class designed to simplify the integration of new rulesets in the future.

---

### `brique.ui.cli`

Contains the classes responsible for the command-line interface.

- **BriqueCLI**  
  Main CLI orchestrator that manages the flow of the game in terminal mode.

---

### `brique.ui.gui`

Contains all GUI-related classes.

Main components:

- **MainMenuScreen**  
  Allows the player to select a game mode.

- **BriqueGUI**  
  Main GUI orchestrator.

- **GameController**  
  Handles communication between the user interface and the game engine.

- **BriqueGameView**  
  Updates the graphical board and pieces based on controller notifications.

- **BoardRenderer**  
  Responsible for rendering the board and handling board interactions.

---

## Development Goals

The project was designed with the following objectives in mind:

- Clean and modular architecture
- Separation of concerns
- Extensibility for future game modes and rulesets
- Support for both CLI and GUI interfaces
- Maintainable and testable code structure
