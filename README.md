mGBA
====

mGBA is a new emulator for running Game Boy Advance games.

Features
--------

- Near full Game Boy Advance hardware support[<sup>[1]</sup>](#missing).
- Fast emulation. Known to run at full speed even on low end hardware, such as netbooks.
- Qt and SDL ports for a heavy-weight and a light-weight frontend.
- Save type detection, even for flash memory size[<sup>[2]</sup>](#flashdetect).
- Real-time clock support, even without configuration.
- A built-in BIOS implementation, and ability to load external BIOS files.
- Turbo/fast-forward support by holding Tab.
- Frameskip, configurable up to 9.
- Screenshot support.
- 9 savestate slots. Savestates are also viewable as screenshots.
- Video and GIF recording.
- Remappable controls for both keyboards and gamepads.
- Loading from ZIP files.
- IPS and UPS support.
- Game debugging via a command-line interface (not available with Qt port) and GDB remote support.

### Planned features

- Local and networked multiplayer link cable support ([Bug #1](https://endrift.com/mgba/bugs/show_bug.cgi?id=1)).
- Dolphin/JOY bus link cable support ([Bug #73](https://endrift.com/mgba/bugs/show_bug.cgi?id=73)).
- Cheat codes ([Bug #58](https://endrift.com/mgba/bugs/show_bug.cgi?id=58)).
- Re-recording support for tool-assist runs. ([Bugzilla keyword "TASBlocker"](https://endrift.com/mgba/bugs/buglist.cgi?quicksearch=TASBlocker))
- Lua support for scripting ([Bug #62](https://endrift.com/mgba/bugs/show_bug.cgi?id=62)).
- A comprehensive debug suite ([Bug #132](https://endrift.com/mgba/bugs/show_bug.cgi?id=132)).
- libretro core for RetroArch and OpenEmu ([Bug #86](https://endrift.com/mgba/bugs/show_bug.cgi?id=86)).


Supported Platforms
-------------------

- Windows Vista or newer
- OS X 10.7 (Lion)[<sup>[3]</sup>](#osxver) or newer
- Linux
- FreeBSD

Other Unix-like platforms work as well, but are untested.

Downloads
---------

Downloads can be found on the official website, in the [Downloads][downloads] section. The source code can be found on [GitHub][source].

Compiling
---------

Compiling requires using CMake 2.8.11 or newer. To use CMake to build on a Unix-based system, the recommended commands are as follows:

	mkdir build
	cd build
	cmake .. -DCMAKE_BUILD_TYPE=Release
	make
	make install

Dependencies that are installed will be automatically detected, and features that are disabled if the dependencies are not found will be shown at the end of the `cmake` command.

### Dependencies

mGBA has no hard dependencies, however, the following optional dependencies are required for specific features. The features will be disabled if the dependencies can't be found.

- Qt 5: for the GUI frontend. Qt Multimedia or SDL are required for audio.
- SDL: for a more basic frontend and gamepad support in the Qt frontend. SDL 2 is recommended, but 1.2 is supported.
- zlib and libpng: for screenshot support and savestate-in-PNG support.
- libedit: for command-line debugger support.
- ffmpeg: or libav for video recording. Libav is untested.
- libzip: for loading ROMs stored in zip files.
- ImageMagick: for GIF recording.

Footnotes
---------

<a name="missing">[1]</a> Currently missing features are

- OBJ window for modes 3, 4 and 5 ([Bug #5](https://endrift.com/mgba/bugs/show_bug.cgi?id=5))
- Mosaic for transformed OBJs ([Bug #9](https://endrift.com/mgba/bugs/show_bug.cgi?id=9))
- Cartridges with light sensors (Boktai: The Sun is in Your Hand and Boktai 2: Solar Boy Django) ([Bug #46](https://endrift.com/mgba/bugs/show_bug.cgi?id=46))

<a name="flashdetect">[2]</a> Flash memory size detection does not work in some cases, and may require overrides, which are not yet user configurable. Filing a bug is recommended if such a case is encountered.

<a name="osxver">[3]</a> 10.7 is only needed for the Qt port. The SDL port is known to work on 10.6, and may work on older.

[downloads]: https://endrift.com/mgba/downloads.html
[source]: https://github.com/mgba-emu/mgba/

Copyright
---------

mGBA is Copyright © 2013 – 2014 Jeffrey Pfau. It is distributed under the [Mozilla Public License version 2.0](https://www.mozilla.org/MPL/2.0/). A copy of the license is available in the distributed LICENSE file.