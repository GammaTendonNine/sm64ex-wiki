## Note to Windows users
Do not attempt to use this guide to compile Windows binaries under WSL. Use the "Compiling on Windows" guide.

## Copy baserom(s) for asset extraction

For each version (jp/us/eu) that you want to build an executable for, put an existing ROM at
`./baserom.<version>.z64` for asset extraction.

## Install build dependencies

The build system has the following package requirements:
  * python3 >= 3.6
  * libsdl2-dev
  * [audiofile](https://audiofile.68k.org/)
  * libglew-dev
  * git


### Debian / Ubuntu - targeting 32 bits
```
sudo apt install build-essential git python3 libaudiofile-dev libglew-dev:i386 libsdl2-dev:i386
```
### Debian / Ubuntu - targeting 64 bits
```
sudo apt install build-essential git python3 libaudiofile-dev libglew-dev libsdl2-dev
```
### Arch Linux
There is an AUR package (courtesy of @narukeh) avaliable under the name [sm64pc-git](https://aur.archlinux.org/packages/sm64pc-git/). Install it using your AUR helper of choice.

If you want to build it yourself:
```
sudo pacman -S base-devel python audiofile sdl2 glew
```

### Void Linux - targeting 64 bits
```
sudo xbps-install -S base-devel python3 audiofile-devel SDL2-devel glew-devel
```

### Void Linux - targeting 32 bits
```
sudo xbps-install -S base-devel python3 audiofile-devel-32bit SDL2-devel-32bit glew-devel-32bit
```

## Build the executable.

Run `make` to build (defaults to `VERSION=us`)

```
make VERSION=jp -j6                           # build (J) version with 6 jobs
make VERSION=us MARCH=i686 TARGET_BITS=32     # builds a (U) 32-bit executable 
make TARGET_RPI=1                             # targets an executable for a Raspberry Pi
```