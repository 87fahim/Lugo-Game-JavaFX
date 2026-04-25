# Ludo Game (JavaFX)

A desktop implementation of a 4-player Ludo game built with Java and JavaFX.

Players take turns rolling a die, moving pieces around the board, capturing opponents on unsafe tiles, and racing all four pieces to their win tile.

## Features

- 4-player turn-based Ludo gameplay
- Animated 3D-like die roll
- Piece movement animation and turn highlighting
- Capture logic on unsafe tiles
- Safe tiles where pieces cannot be captured
- Automatic move when only one valid piece is available
- In-game player color change
- Restart button to reset the match

## Tech Stack

- Java
- JavaFX (`javafx.controls`)
- Project layout compatible with Eclipse/VS Code Java workflows

## Project Layout

Main source root:

`LudoKing/src`

Packages:

- `main`: app entry point, UI shell, dice roll event flow
- `board`: board generation, tiles, arrows, start/win zones
- `player`: player abstractions and implementations per player
- `piece`: piece model and behavior
- `die`: die and cube visuals
- `newludo`: game composition/initialization
- `util`: shared gameplay and UI helper logic

## Entry Point

Main class:

`main.LudoKing`

Source file:

`LudoKing/src/main/LudoKing.java`

## Requirements

1. JDK 17 or newer (Java 11+ can work if JavaFX setup is correct)
2. JavaFX SDK installed locally
3. JavaFX `lib` folder path available for compile/run module path

Example JavaFX SDK path on Windows:

`C:\Program Files\Java\javafx-sdk-26.0.1\lib`

## Run in VS Code (Recommended)

This project already includes VS Code tasks in:

`LudoKing/.vscode/tasks.json`

The tasks:

- `Compile Ludo Game`
- `Run Ludo Game`

### Important

If your JavaFX SDK is installed in a different location, update the `--module-path` value in `LudoKing/.vscode/tasks.json`.

## Build and Run from Terminal

From `LudoKing` directory:

```powershell
javac -d bin -sourcepath src --module-path "C:\Program Files\Java\javafx-sdk-26.0.1\lib" --add-modules javafx.controls src/main/LudoKing.java
java --module-path "C:\Program Files\Java\javafx-sdk-26.0.1\lib" --add-modules javafx.controls -cp bin main.LudoKing
```

## How to Play

1. The game starts with 4 players and each has 4 pieces in home.
2. Click the die to roll.
3. Click a highlighted movable piece to play that move.
4. If a piece lands on an opponent on an unsafe tile, the opponent piece returns to home.
5. Safe tiles protect pieces from capture.
6. Rolling a 6 can grant another move opportunity according to the current move logic.
7. A player wins after all 4 pieces reach the player's win tile.
8. The game ends when only one player remains unfinished.

## Controls

- Click die: roll
- Click highlighted piece: move selected piece
- `Restart!`: start a fresh match
- `Change Color`: open color picker for the active player

## Notes

- `EndGameAnimation` exists but is not fully integrated.
- Game logic and visuals are contained in one desktop application (no network/multiplayer backend).

## Troubleshooting

### Error: JavaFX modules not found

- Verify JavaFX SDK is installed.
- Confirm `--module-path` points to the correct JavaFX `lib` directory.
- Ensure `--add-modules javafx.controls` is present in both compile and run commands.

### App compiles but does not launch in IDE

- Check project SDK/JDK selection.
- Rebuild (`bin` output) after correcting module path.
- Run compile task first, then run task.

## Future Improvements

- Complete end-game animation flow
- Add unit tests for movement/collision rules
- Add sound effects and richer UI themes
- Add configurable player count and rule variants

## License

No license file is currently provided in this repository.
If you plan to distribute or reuse this project, add a license (for example, MIT) to clarify usage rights.
