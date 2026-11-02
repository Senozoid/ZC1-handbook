# Getting Started

The game is under development, only pre-releases are currently available. After the first test release (see [version numbering](#version-numbering)), it should be on Itch. If you get the game through the Itch desktop app, it takes care of everything; you can download, launch, or delete the game, right from the app. Otherwise, follow the links and instructions here.

## Download

| OS            | GitHub                                                                                          | Itch |
| ------------- |:-----------------------------------------------------------------------------------------------:|:----:|
| Windows (x64) | [v0.1.0](https://github.com/Senozoid/ZC1-handbook/releases/download/v0.1.0/zc1-windows-x64.zip) | --   |
| Linux (x64)   | [v0.1.0](https://github.com/Senozoid/ZC1-handbook/releases/download/v0.1.0/zc1-linux-x64.tgz)   | --   |

## Play on Windows

Download the zip file (links above) and extract its contents to any location of your choice. To launch the game, go to that folder and double-click on the `Shadow-of-Doom.exe` file. Optionally, you can make a desktop shortcut for convenience.

**NOTE:** Since this is a relatively unknown software (no code signing certificate), Windows might warn you against running it. To put your mind at ease, you can first scan it with Microsoft Defender or any security software you trust. You can also check the download URL directly with web utilities like [VirusTotal](https://www.virustotal.com/gui/home/url).

## Play on Linux

Download the tgz file (links above), extract its contents, and make the `zc1` file executable. To launch the game, run the same file through the terminal. Optionally, create a desktop entry.

If it helps, you can use the following scripts, replacing all occurrences of `<game-dir>` with the actual path where you would keep the game files.

---

1. Download the tgz file and open the terminal in the directory where it is downloaded. Then, run the following commands (replace `<game-dir>`):
   
   ```bash
   mkdir -p <game-dir>
   tar -xzvf zc1-linux-x64.tgz -C <game-dir>
   chmod +x <game-dir>/zc1
   ```

2. To launch the game, run the following commands on the terminal (replace `<game-dir>`):
   
   ```bash
   cd <game-dir>
   ./zc1
   ```

3. You can also create a desktop entry to make it easier for yourself to launch the game. To know how, see `README-for-linux.md` in the game directory.

## Deletion

The game deliberately keeps all files within its own folder (don't launch it from anywhere else). To delete the game cleanly, just delete its entire folder (and the desktop shortcut, if you made one). You can keep a backup of the `saves` folder if you wish.

## Version Numbering

### Pre-release (alpha)

+ The first number is `0` (Examples: `v0.2`, `v0.1.2` etc.)
+ Earliest releases of the game, during initial development
+ Guaranteed to be incomplete, published solely for informational purposes

### Test release (beta)

+ The first number is `1` or more, and there is a `.x` or `.X` suffix (Examples: `v2.x`, `v1.2.X`, `v1.2.3.x` etc.)
+ Expected to have bugs, published mostly for testing purposes

### Stable release

+ The first number is `1` or more, and there is no letter suffix (Examples: `v2.0.0`, `v1.2.3` etc.)
+ If two stable releases differ by the first or second number, their saves are expected to be incompatible

## Initial Configuration

## Character Creation

## Gameplay Basics

## First Playthrough Tips
