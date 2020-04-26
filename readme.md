# noiz2sdl2

noiz2sa shooting game with some updates for modern systems.

- Display in desktop resolution instead of 640x480x8bpp which is not well supported anymore
- Use a modern rendering API so it can be recognized by video recording software (e.g. OBS Studio)

## New command line options

| Option        | Description                                               |
| ------------- | --------------------------------------------------------- |
| -scalelinear  | Apply linear filtering to scaled image - default off      |
| -scaleinteger | Scale only by integer factors (2x, 3x, ...) - default off |

## Compiling

Install SDL2 and SDL2_mixer dev libraries and premake4. Then

```bash
git clone --recurse-submodules https://github.com/ioribranford/noiz2sdl2.git
cd noiz2sdl2/src
cd bulletml
cp premake.lua premake4.lua
premake4 gmake
make -j
cd ..
make -j
cp noiz2sa.exe ..
```

## Credits

Original game by ABA Games http://www.asahi-net.or.jp/~cs8k-cyu/windows/noiz2sa_e.html