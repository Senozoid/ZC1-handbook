# Getting Started

**WIP: The links will be available after release.**

The easiest way to start playing is to [download the game on Windows](https://github.com/Senozoid/ZC1-handbook/releases/latest/download/zc1-setup.exe), run the downloaded installer, and launch the game from the desktop shortcut that appears.

If you are not comfortable with running an installer, you can also [download the zipped version for Windows](https://github.com/Senozoid/ZC1-handbook/releases/latest/download/zc1-win.zip), extract it, and run the given launcher.

If you are not on Windows, you may be able to [download the tgz version](https://github.com/Senozoid/ZC1-handbook/releases/latest/download/zc1-uni.tgz), extract it and run `./Launcher` in the game folder. However, if you have a Windows machine, **I recommend playing on Windows**. I have tested the tgz version only on one Linux system, and although it could, I cannot guarantee that it will work on macOS. Any advice or help with testing will be very appreciated, so feel free to email me about this. I have plans to use either [packr](https://github.com/libgdx/packr) or [jpackage](https://docs.oracle.com/en/java/javase/17/docs/specs/man/jpackage.html) to build installers for Linux and macOS in the future, and any advice about that will be appreciated as well.

## Downloading

**After the game is released**, you should be able to download the Windows version from:

- [GitHub](https://github.com/Senozoid/ZC1-handbook/releases/latest/download/zc1-setup.exe)
- [Itch\.io]()
- [Game Jolt]()

## Installation

> **NOTE:** If you get the game through the Itch desktop app, it takes care of your installation automatically. Otherwise, follow the instructions here.

### Executable Installer for Windows (`.exe`)

If you want to make the setup process as simple as possible, the executable installer is the better option. It installs the game on your computer, automatically creates shortcuts to launch it, and gives you the option to uninstall it later from "Apps & features" in Windows Settings (or "Programs and Features" in Control Panel).

Run the installer you downloaded and follow the prompts on the screen. You can choose the installation location and whether to create shortcuts on the desktop and in the start menu, and the installer will take care of everything. To play the game, just use any of the installed shortcuts.

### Portable Zip for Windows (`.zip`)

The portable zip is a pre-installed folder compressed into a zip file, which is the better option if you want to install your game on removable media like a flash drive, so that you can continue your playthrough on a different computer later.

Just unzip the downloaded file into the location of your choice and you are all set. You can play the game by running the "Launcher.exe" file in the created folder. You can move and rename the folder as you wish without any problems. If you want to create a desktop shortcut, you have to do so manually. To uninstall the game, just delete the installation folder.

### Installing on macOS or Linux (`.tgz`)

> **NOTE 1:** If you have a Windows machine, I recommend playing there instead. See the top of this page for more details.

> **NOTE 2:** The game needs you to have bash, which is probably already in your system by default. But you can confirm this by running `cat /etc/shells` on the terminal and seeing if "/bin/bash" is listed.

The UNIX version is just the game directory compressed into a tgz (tar.gz) file, very similar to the portable zip for Windows. To install, extract it into the location of your choice and change permissions so that you can execute the files in the game directory. After that, you can play the game just by running the "Launcher" file in the directory.

If you are not sure how to do all that, just replace the "filename" and "installation-path" in the following commands, and run them on the terminal. If there are any problems with these commands, please [let me know](../introduction.html#report-problems).

Setup:

```bash
tar -xzvf filename.tgz -C installation-path
chmod +x installation-path/Launcher
```

Launch:

```bash
cd installation-path
./Launcher
```

## Initial Setup

## Character Creation

## Gameplay Basics

## First Playthrough Tips
