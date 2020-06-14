### Set up MSYS2.

Follow [this guide](https://github.com/orlp/dev-on-windows/wiki/Installing-GCC--&-MSYS2). You might want to download a newer version of the MSYS2 installer from [here](https://github.com/msys2/msys2-installer/releases) instead of the link used in that guide.

Run the `MINGW64` prompt if you wish to build a 64-bit version of the executable, or the `MINGW32` prompt otherwise.

### Install dependencies.

```
pacman -S mingw-w64-i686-glew mingw-w64-x86_64-glew mingw-w64-i686-SDL2 mingw-w64-x86_64-SDL2 python3
```

### Copy baserom(s) for asset extraction

For each version (jp/us/eu) that you want to build an executable for, put an existing ROM at
`./baserom.<version>.z64` for asset extraction.

### Navigate to the sm64pc root directory.

### Run `make`. To turn certain features on and off, append any needed [build flags](https://github.com/sm64pc/sm64pc/wiki/Build-options) to your `make` invocation like so:

```
make EXTERNAL_DATA=1
```