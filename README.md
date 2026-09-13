# d/BASIC

**The BASIC that QuickBASIC grew up into.** QuickBASIC structure, VB-style classes,
modern determinism, one compiled program file that runs in the browser, on the
desktop, and on the 8-bit home computers d/OS runs on. Line numbers welcome.

- **Try it now:** https://dbasic.kallinnovations.com/playground/
- **Guide, tutorials, the 96 classic listings:** https://dbasic.kallinnovations.com/
- **Downloads:** the [Releases](../../releases) page on this repository

This repository holds the downloadable releases only. The source is not published.

## Downloads

Each release carries:

| Archive | What it is |
| --- | --- |
| `dbasic-<version>-macos-universal.zip` | the `dbasic` compiler, runtime and window host, universal (Apple silicon and Intel), with the d/Works widget and GX game libraries and the examples |
| `dbasic-<version>-linux-x64.tar.gz` | the same kit for Linux x86-64 (console programs today; window hosts to come) |
| `dbasic-<version>-windows-x64.zip` | the same kit for Windows x86-64 (console programs today; window hosts to come) |
| `dbasic-<version>-wasm.zip` | the compiler and runtime as WebAssembly with the playground page, for embedding in your own site |

Every archive has a `manifest.json` with the source commit and the SHA-256 of every
file, and the release notes list the SHA-256 of each archive.

## Licence

Free to download and use, including commercially. **What you build with it is yours:**
no royalty, no attribution, no licence terms attach to your programs. The toolchain
itself is not open source; see [LICENSE.txt](LICENSE.txt). Third-party components
(the fonts, and shared code listed in each archive's `third_party/`) keep their own
licences.

© 2026 Kall Innovations, LLC
