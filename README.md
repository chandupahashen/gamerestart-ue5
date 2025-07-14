# GameRestart Unreal Engine Plugin

## Overview
GameRestart is a utility plugin for Unreal Engine 5 that provides Blueprint-accessible functions to programmatically quit and restart the game executable. It is designed for Windows platforms and can optionally restart the game and open a specific level.

## Features
- **Quit and Restart Game**: Cleanly exits the running game and relaunches the executable after a short delay.
- **Restart and Open Level**: Restarts the game and passes a level name as a command-line argument to open a specific level on startup.
- **Blueprint Library**: All functions are exposed to Blueprints for easy integration.

## How It Works
- The plugin creates a temporary batch file in the executable's directory.
- The batch file waits for a short delay, relaunches the game executable (optionally with a level argument), deletes itself, and then exits.
- The plugin launches this batch file using `cmd.exe` and then requests the game to quit.

## Usage
1. **Add the Plugin**: Place the `GameRestart` plugin folder in your project's `Plugins` directory.
2. **Enable the Plugin**: Enable `GameRestart` in the Unreal Editor's Plugins window.
3. **Blueprint Integration**:
   - Use the `QuitAndRestartGame` node to restart the game.
   - Use the `RestartGameAndOpenLevel` node to restart and open a specific level (provide the level name as a string).

## Example
- To restart the game from Blueprint, simply call `QuitAndRestartGame`.
- To restart and open a level named `MainMenu`, call `RestartGameAndOpenLevel` with `MainMenu` as the argument.

## Platform Support
- **Windows only** (uses batch files and Windows-specific process management).

## Notes
- The plugin creates and deletes temporary batch files in the executable's directory.
- The restart delay is set to 2 seconds to allow the current process to exit before relaunching.
- Level names passed to `RestartGameAndOpenLevel` should not include file extensions.

## License
Copyright Epic Games, Inc. All Rights Reserved.

## Support
For questions or issues, please open an issue on your project's repository or contact the plugin author.
