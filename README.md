PokoHex (fork)
=====

![License](https://img.shields.io/badge/License-GPLv3-blue.svg)

Fork of [berichan/PokoHex](https://github.com/berichan/PokoHex), a proof of concept save editor for Pokopia (Poko a Pokemon).

Edits savedata dumped from the Nintendo Switch 2.

* Bring your own save file data; this program does not dump it from your console.

## What this fork adds

* **File → Save (Ctrl+S)** writes your edits back to the save folder you opened, so you don't need a new empty folder for every export.
  * Before writing, it copies the whole save folder to `Documents\PokoHex Backups\<timestamp>`.
  * Each file is written through a temporary file and re-read afterwards to check it matches.
  * It writes every edited file, including the player data and any edited map stages.
* **File → Export save copy (Ctrl+Shift+S)** still works as before: it writes the edited save to a new, empty folder and leaves the original untouched.
* Based on upstream PokoHex 0.2.1, which includes the Player (Skills and Reactions), Items, Villagers and Map editors.

Close the game (or go back to the title screen) before saving over a save that an emulator is using. If the file is locked, PokoHex shows an error and changes nothing.

## Building from source

Requires the .NET 10 SDK.

    git clone https://github.com/protos813-spec/PokoHex.git
    cd PokoHex
    dotnet build PokoHex.slnx -c Release
    dotnet publish PokoHex -c Release -r win-x64 --self-contained true -p:PublishSingleFile=true -o out

The editor is then `out\PokoHex.exe`.

## Upstream

**Windows**: Download `PokoHex-win-x64.zip` from the [upstream Releases](https://github.com/berichan/PokoHex/releases), extract it, and run `PokoHex.exe`.

**All Platforms/Browser**: Use the upstream GitHub Pages, click here -> [PokoHex.Web](https://berichan.github.io/PokoHex/)

## Other

Based on the style of [NHSE](https://github.com/kwsch/NHSE)

**We do not support or condone cheating at the expense of others.** Please be responsible!

> [!WARNING]
> Always keep save backups of your save from your console and edits before editing or restoring any savefiles!