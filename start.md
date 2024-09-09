# Getting Started

**The game is under development; Itch and Game Jolt links will be available after the first test release.**

> **NOTE:** If you get the game through the Itch desktop app, it sets up everything automatically, and you can launch the game through the app. Otherwise, follow the links and instructions here.

## Download

| OS            | Itch | GitHub                                                                                       | Game Jolt |
| ------------- |:----:|:--------------------------------------------------------------------------------------------:|:---------:|
| Windows (x64) | --   | [zip](https://github.com/Senozoid/ZC1-handbook/releases/latest/download/zc1-windows-x64.zip) | --        |
| Linux (x64)   | --   | [tgz](https://github.com/Senozoid/ZC1-handbook/releases/latest/download/zc1-linux-x64.tgz)   | --        |

## Play on Windows

1. To setup, download the zip file from one of the given links and extract its contents to any location of your choice.

2. To launch the game, go to the game directory (where you extracted the files). There, double-click on the `Shadow-of-Doom.exe` file to run it.

3. Optionally, you can make a desktop shortcut to be able to launch the game more easily.

## Play on Linux

If you have a Windows machine, _I recommend playing on Windows_. The Linux version is not thoroughly tested. Any help or advice regarding this is appreciated.

> **NOTE:** In the following scripts, replace all occurrences of `<game-dir>` with the actual path where you would keep the game files.

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

### Stable release

+ Marked by 3 numbers, i.e., update (major; `>=1`), patch (minor), and story version [Examples: `v2.0.0`, `v1.2.3` etc.]
+ Finished versions released to the publishing platforms, and meant to be played by most players
+ If two stable releases differ only by the story version, the saves from each are compatible with the other
+ If two stable releases differ by patch, their saves are not guaranteed to be compatible
+ If two stable releases differ by update, their saves are expected to be incompatible
+ Hopefully, there will not be any (major) updates after the first stable release, but (minor) patches are to be expected

### Test release

+ Suffixed with `.x` or `.X` [Examples: `v2.x`, `v1.2.X`, `v1.2.3.x` etc.]
+ Expected to be followed by a stable release
+ Expected to have bugs, published mostly for testing purposes

### Pre-release

+ The first number is `0` [Examples: `v0.2`, `v0.1.2` etc.]
+ Earliest releases of the game
+ Guaranteed to be incomplete, published solely for informational purposes

## Initial Configuration

## Character Creation

## Gameplay Basics

## First Playthrough Tips
