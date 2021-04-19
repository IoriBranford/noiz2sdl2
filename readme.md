# noiz2sdl2

noiz2sa shooting game with some updates for modern systems.

- Display in desktop resolution and 32-bit color, instead of 640x480x8bpp which is not well supported on current hardware
- Use OpenGL so it can work with recording and post-processing software

## Installing

Download the latest release for Windows [HERE](https://github.com/IoriBranford/noiz2sdl2/releases/latest)

On other OSes, see Compiling below.

## New command line options

| Option        | Description                                               |
| ------------- | --------------------------------------------------------- |
| -scalelinear  | Apply linear filtering to scaled image - default off      |
| -scaleinteger | Scale only by integer factors (2x, 3x, ...) - default off |

## Compiling

On OSX or Linux open a terminal. On Windows, install MSYS2, and open the "MSYS2 MinGW 64-bit" terminal.

### Prep

Checkout this repo: `git clone --recurse-submodules https://github.com/ioribranford/noiz2sdl2.git`

Install SDL2 and SDL2_mixer dev libraries. Examples:

- Ubuntu, Debian: `sudo apt install libsdl2-dev libsdl2-mixer-dev`

- MSYS2: `pacman -S mingw-w64-x86_64-SDL2 mingw-w64-x86_64-SDL2_mixer`

### Build

```bash
# Build bulletml
cd noiz2sdl2/src/bulletml
./setup.sh
config=release make

# Build game
cd ..
make
cp noiz2sa.exe ..
```

## Credits

Original game by ABA Games http://www.asahi-net.or.jp/~cs8k-cyu/windows/noiz2sa_e.html
