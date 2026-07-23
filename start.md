# Getting Started

If you get the game through the Itch desktop app, it takes care of everything; you can download, install and launch the game, right from the app. Otherwise, follow the links and instructions here.

## Download

> **NOTE:** The game is under development; Itch and Game Jolt links will be available after the first test release. See [version numbering](#version-numbering) for more details.

---

| OS            | Itch | GitHub                                                                                          | Game Jolt |
| ------------- |:----:|:-----------------------------------------------------------------------------------------------:|:---------:|
| Windows (x64) | --   | [v0.1.0](https://github.com/Senozoid/ZC1-handbook/releases/download/v0.1.0/zc1-windows-x64.zip) | --        |
| Linux (x64)   | --   | [v0.1.0](https://github.com/Senozoid/ZC1-handbook/releases/download/v0.1.0/zc1-linux-x64.tgz)   | --        |

## Play on Windows

1. To setup, download the zip file from one of the given links and extract its contents to any location of your choice.

2. To launch the game, go to the game directory (where you extracted the files). There, double-click on the `Shadow-of-Doom.exe` file to run it.

3. Optionally, you can make a desktop shortcut to be able to launch the game more easily.

## Play on Linux

If you have a Windows machine, _I recommend playing on Windows_. The Linux version is not thoroughly tested. Any help or advice regarding this is appreciated.

> **NOTE:** In the following scripts, replace all occurrences of `<game-dir>` with the actual path where you would keep the game files.

---

1. To setup, download the tgz file and open the terminal in the directory where it is downloaded. Then, run the following commands (replace `<game-dir>`):
   
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

## Version Numbering

### Pre-release

+ The first number is `0` [Examples: `v0.2`, `v0.1.2` etc.]
+ Earliest releases of the game, during initial development
+ Guaranteed to be incomplete, published solely for informational purposes

### Test release

+ Suffixed with `.x` or `.X` [Examples: `v2.x`, `v1.2.X`, `v1.2.3.x` etc.]
+ Expected to be followed by a stable release
+ Expected to have bugs, published mostly for testing purposes

### Stable release

+ Marked by 3 numbers, i.e., major (`>=1`), minor, and content update numbers respectively [Examples: `v2.0.0`, `v1.2.3` etc.]
+ If two stable releases differ only by content update, the saves from each are compatible with the other, unless mentioned otherwise
+ If two stable releases differ by major or minor update, their saves are expected to be incompatible

## Initial Configuration

## Character Creation

## Gameplay Basics

## First Playthrough Tips
