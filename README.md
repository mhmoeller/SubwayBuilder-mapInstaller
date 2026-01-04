# SubwayBuilder-mapInstaller
Installs single maps to the mod API

## Features
Automated Installer: Includes a custom Node.js script that automatically places large data files in the correct game directories (cities/data/CPH) while keeping the mod manageable.
Downloads pmtiles executable to serve the map tiles so you can see your map in game.
Portable Map Server: Generates a serve.bat file that makes hosting the local map tiles (PMTiles) easy.

## Requirements
Subway Builder (the game)
Node.js (Required to run the installer script)
The files from this repository.
A map which is made for this installer.

## Installation
The installation process is automated to ensure all data files end up in the correct folders.

1. Open the game, go to the Settings and enable modding. Press the Open Mods Folder.

2. Create a folder and name it mapInstaller

3. Download the latest release of the installer (ZIP file).
   Press the green "<> code" button and Download ZIP.

5. Unzip the content into your game's Mods folder

6. Download the map you want to the same folder as the mapInstaller

7. Run the Installer:

#### Windows:
Double-click install.bat inside the CPH folder.
#### macOS:

Method 1 (Recommended): Open Terminal, navigate to the CPH folder and run:
```
./install.sh
```
Method 2: Right-click install.sh, select "Open With" → "Terminal"

Method 3: In Finder, open the CPH folder, then open Terminal and drag install.sh into the Terminal window, press Enter

#### Linux:

Open a terminal in the CPH folder and run:
```
chmod +x install.sh
./install.sh
```
Wait for the script to finish. It will:
Move the heavy data files (.gz) to the cities/data/CPH folder.
Generate a serve.bat file for you.

## How to Play
Start the Map Server:
Locate the serve.bat file (created by the installer in the mod folder).
Tip: You can move serve.bat to your Desktop for easy access.
Double-click it to start the local server. Keep this window open while playing.
Start the Game:
Open Subway Builder.
Go to Mods and enable the map (if listed).
Close the game entirely.
Restart the game.
Start a New Game and find your map under modded in New Game.

### Notes
Data Files: The installer moves ocean_depth_index.json.gz, roads.geojson.gz, buildings_index.json.gz, etc., to the game's internal data structure.

Map Server: The pmtiles.exe utility is downloaded to serve the map tiles locally. The serve.bat script launches this on port 8081 with CORS enabled, which is required for the game to display the background map.

Uninstalling: To remove the map, delete the map folder from your mods directory and delete the map folder from %APPDATA%\metro-maker4\cities\data\. And then delete the mapInstaller directory.
