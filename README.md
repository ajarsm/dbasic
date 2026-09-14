# d/BASIC

**The BASIC that QuickBASIC grew up into.** QuickBASIC structure, VB-style classes,
modern determinism, one compiled program file that runs in the browser, on the
desktop, and on the 8-bit home computers d/OS runs on. Line numbers welcome.

- **Try it now:** https://dbasic.kallinnovations.com/playground/
- **Guide, tutorials, the 96 classic listings:** https://dbasic.kallinnovations.com/
- **Downloads:** the [Releases](../../releases) page on this repository

This repository holds the downloadable releases only. The source is not published.

## Quick start

Download the kit for your machine from [Releases](../../releases), unpack it, and open a
terminal inside the folder. The folder is self-contained and can live anywhere;
`bin/dbasic` is the compiler, the runtime and the window host in one.

**macOS** (the kit is not yet notarized; the first command clears the download flag):

```
xattr -dr com.apple.quarantine .
./bin/dbasic run examples/oop-window-hello.bas   # opens a window
```

**Linux** (the runtime links ALSA for sound):

```
sudo apt install libasound2t64                   # or libasound2 on older releases
./bin/dbasic run examples/oop-sombrero.bas
```

**Windows** (PowerShell or Command Prompt):

```
.\bin\dbasic.exe run examples\oop-sombrero.bas
```

Write `hello.bas`, run it, compile it, run the compiled file:

```
./bin/dbasic run hello.bas                       # compile in memory and run
./bin/dbasic build hello.bas -o out/hello.dbc    # compile to a program file
./bin/dbasic exec out/hello.dbc                  # run the compiled program
```

`IMPORT dworks.widgets` and `IMPORT gx` compile the widget and game libraries in from
`libraries/`. What works where in this release: macOS has console programs, `INPUT`,
native windows, d/Works widgets, GX, copy/paste, drag and drop, files, sound and
network; Linux has console programs, `INPUT`, native windows, d/Works widgets, GX,
files, sound and network; Windows has console programs, native windows, d/Works
widgets, GX, files and network (`INPUT` to come). Native windows need a display;
copy/paste and drag and drop with other applications are macOS-only for now.

## The applications

Every kit's `apps/` folder has the five d/BASIC applications as compiled programs,
ready to run:

| application | what it is | source |
| --- | --- | --- |
| Calculator | a d/Works calculator | included |
| d/Calc | a spreadsheet | included |
| d/Write | a document editor | included |
| Cantor | a 1-bit adventure in seven cantos | program only |
| Star Commander | a space-combat game | program only |

```
./bin/dbasic exec apps/calculator/CALC-W16.DBC
./bin/dbasic exec --data-mount apps/dcalc/data apps/dcalc/D-CALC.DBC
./bin/dbasic exec --data-mount apps/dwrite/data apps/dwrite/D-WRITE.DBC
./bin/dbasic exec --file-mount apps/cantor/files apps/cantor/CANTOR.DBC
./bin/dbasic exec apps/star-commander/STARCMDR.DBC
```

`--data-mount` names the folder d/Calc and d/Write save into (the kit ships an empty
one); `--file-mount` names the folder Cantor's pictures, sound and saved games live in.
The games need a machine with audio output.

## Editor support

`dbasic-0.1.0.vsix` on the [Releases](../../releases) page is a Visual Studio Code
extension: highlighting, diagnostics, formatting, symbols, go-to-definition, rename,
hover, completion and Build/Run/Trace tasks. Install it from the file (Command
Palette → **Extensions: Install from VSIX...**), then point `dbasic.server.path` at the
kit's `bin/dbasic` (`bin\dbasic.exe` on Windows) or put that `bin` on your `PATH`. The
language server is the compiler itself, so what the editor says is what `build` says.
One `.vsix` serves macOS, Windows and Linux.

## Downloads

Each release carries:

| Archive | What it is |
| --- | --- |
| `dbasic-<version>-macos-universal.zip` | the `dbasic` compiler, runtime and window host, universal (Apple silicon and Intel), with the d/Works widget and GX game libraries, the examples and the five applications |
| `dbasic-<version>-linux-x64.tar.gz` | the same kit for Linux x86-64 |
| `dbasic-<version>-windows-x64.zip` | the same kit for Windows x86-64 |
| `dbasic-<version>-wasm.zip` | the compiler and runtime as WebAssembly with the playground page, for embedding in your own site |
| `dbasic-<version>.vsix` | the Visual Studio Code extension, installed from the file; needs one of the kits above for its language server |

Every archive has a `manifest.json` with the source commit and the SHA-256 of every
file, and the release notes list the SHA-256 of each archive.

## Licence

Free to download and use, including commercially. **What you build with it is yours:**
no royalty, no attribution, no licence terms attach to your programs. The toolchain
itself is not open source; see [LICENSE.txt](LICENSE.txt). Third-party components
(the fonts, and shared code listed in each archive's `third_party/`) keep their own
licences.

© 2026 Kall Innovations, LLC
