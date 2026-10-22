# OneKnightStand
<img width="700" height="513" alt="image" src="https://github.com/user-attachments/assets/6e55f5b9-4237-40d9-844c-13845354ae80" />

A local multiplayer NES ninja fighting game written in NESfab.

## Build

Install NESfab 1.8, then from the repository root run:

```sh
./build.sh
```

If the compiler is not named `nesfab-1-8.exe` in the repository root, pass it with `NESFAB`:

```sh
NESFAB=/path/to/nesfab-1-8.exe ./build.sh
```

Or run NESfab directly:

```sh
wine /path/to/nesfab-1-8.exe oneknightstand.cfg
```

The ROM is written to `oneknightstand.nes`.

## Notes

- `yee2.mapfab` is the current map source.
- `tile-set-greyscale.png` is the active tileset source used by the build.

## Copyright

Copyright © 2026 Niklas Pettersson. All rights reserved.

Original code and artwork may not be reused, modified, or
redistributed without written permission.

Third-party components retain their respective licenses.
See `lib/LICENSE_1_0.txt` for the NESfab library license.
