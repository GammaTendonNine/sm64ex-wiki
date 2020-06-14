## Note to Windows users
Do not attempt to use this guide to compile Windows binaries under WSL or Linux. It will not work. Use the "Compiling on Windows" guide.

## Copy baserom(s) for asset extraction

For each version (jp/us/eu) that you want to build an executable for, put an existing ROM at
`./baserom.<version>.z64` for asset extraction.

## Install build dependencies

The build system has the following package requirements:
  * python3 >= 3.6
  * libsdl2-dev
  * libglew-dev
  * git

### Debian / Ubuntu - targeting 32 bits
```
sudo apt install build-essential git python3 libglew-dev:i386 libsdl2-dev:i386
```
### Debian / Ubuntu - targeting 64 bits
```
sudo apt install build-essential git python3 libglew-dev libsdl2-dev
```
### Fedora - targeting 64 bits
```
sudo dnf install make gcc python3 glew-devel SDL2-devel
```
### Fedora - targeting 32 bits
```
sudo dnf install python3.i686 glew-devel.i686 SDL2-devel.i686
```
### Arch Linux
There is an AUR package (courtesy of @narukeh) avaliable under the name [sm64pc-git](https://aur.archlinux.org/packages/sm64pc-git/). Install it using your AUR helper of choice.

If you want to build it yourself:
```
sudo pacman -S base-devel python sdl2 glew
```

### Void Linux - targeting 64 bits
```
sudo xbps-install -S base-devel python3 SDL2-devel glew-devel
```

### Void Linux - targeting 32 bits
```
sudo xbps-install -S base-devel python3 SDL2-devel-32bit glew-devel-32bit
```

## Build the executable.

Run `make` to build. To turn certain features on and off, append any needed build flags to your `make` invocation like so:
```
make BETTERCAMERA=1 EXTERNAL_DATA=1 -j4
```
