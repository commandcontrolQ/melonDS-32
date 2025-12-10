<p align="center"><img src="https://raw.githubusercontent.com/commandcontrolQ/melonDS-32/master/res/icon/melon_128x128.png"></p>
<h2 align="center"><b>melonDS</b></h2>
<p align="center">
</p>

> [!WARNING]
> This fork of melonDS is for 32-bit systems **only!** <br>
> If you are able to run 64-bit programs, theres a very good chance you are better off with [the official melonDS repository.](https://github.com/melonDS-emu/melonDS)

DS emulator, sorta

The goal is to do things right and fast, akin to blargSNES (but hopefully better). But also to, you know, have a fun challenge :)
<hr>

## Usage/TODO

For how to use melonDS (and also what is planned for the future) please refer to [the official repository.](https://github.com/melonDS-emu/melonDS)

## Build

For now, <i>the instructions are for Windows only.</i>

1. Install [MSYS2](https://www.msys2.org/)
2. Open the **MSYS2 MinGW 32-bit** terminal
3. Update the packages using `pacman -Syu` and reopen the terminal if it asks you to
4. Download the repository:
   ```bash
   pacman -S git
   git clone https://github.com/commandcontrolQ/melonDS-32.git && cd melonDS-32
   ```
6. Install the required dependencies:
   ```bash
   pacman -S i686-missing/*
   pacman -S make mingw-w64-i686-{toolchain,cmake,SDL2,libarchive,enet,zstd,faad2}
   ```
7. Configure and make:
   ```bash
   mkdir build && cd build
   cmake -B build -DBUILD_STATIC=ON -DUSE_QT6=OFF -DCMAKE_PREFIX_PATH=$MSYSTEM_PREFIX/qt5-static -DCMAKE_BUILD_TYPE=Release ..
   cmake --build build -j$(nproc --all)
   ```


## Credits

 * Martin for GBAtek, a good piece of documentation
 * Cydrak for the extra 3D GPU research
 * limittox for the icon
 * All of you comrades who have been testing melonDS, reporting issues, suggesting shit, etc

## Licenses

[![GNU GPLv3 Image](https://www.gnu.org/graphics/gplv3-127x51.png)](http://www.gnu.org/licenses/gpl-3.0.en.html)

melonDS is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

### External
* Images used in the Input Config Dialog - see `src/frontend/qt_sdl/InputConfig/resources/LICENSE.md`
