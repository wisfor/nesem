# NESem

!NESem is forked from [LiteNES](https://github.com/NJU-ProjectN/LiteNES) and is being developed further by adding a nice GUI and such!

NESem runs classical roms (e.g., Battle City, Yie Ar Kung-Fu and Super Mario),
but has only partial support of NES roms, and does not support the emulation of APU.

The key feature of NESem is its *portability*:
the system-call-dependent code is reduced to minimal
(only appears in `hal.c` and `main.c`).
All other sources *do not contain any direct or indirect calls to the operating system kernel*.
Also, the only calls to standard C library are memory movements (e.g., `memcpy` and `memcmp`).
To port NESem to other systems, only slight modification of `main.c` and re-implementation of `hal.c` is required.

### Compilation

To compile NESem, you must have *allegro5* library.
Usually you can install it in the official software repository
(by `apt-get`, `yum`, `pacman` or `emerge`, depending on your Linux
distribution).
For Ubuntu users, if you cannot find allegro5 in your sources, please find 
`liballegro5.0` and `liballegro5-dev` deb package and install them.

Type `make` in the command line to compile. Resolve any error message until
the `litenes` binary file is created.

### Game Play

You need to prepare a NES rom first.
Assume it (`rom.nes`) is located in the same directory as the LiteNES binary.
Then in this directory, type `./litenes rom.nes` to start the emulator.

Key bindings: UP - `W`, DOWN - `S`, LEFT - `A`, RIGHT - `D`, SELECT - `U`,
START - `I`, A - `K` and B - `J`. Only one player is supported.
Type `CTRL C` in terminal to exit.
