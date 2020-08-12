### Set up MSYS2.

Download the newest version of the MSYS2 installer from [here](https://github.com/msys2/msys2-installer/releases) and install it.

Run the `MINGW64` prompt if you wish to build a 64-bit version of the executable, or the `MINGW32` prompt otherwise.

Enter `pacman -Syuu` in the prompt and hit Enter. Press `Y` when it asks if you want to update packages. If it asks you to close the prompt, do so, then restart it and run the same command again. This updates the packages to their latest versions.

### Install dependencies.

Enter this command to install packages necessary to build sm64ex:

```
pacman -S unzip make git mingw-w64-i686-gcc mingw-w64-x86_64-gcc mingw-w64-i686-glew mingw-w64-x86_64-glew mingw-w64-i686-SDL2 mingw-w64-x86_64-SDL2 python3
```

### Copy baserom(s) for asset extraction

For each version (jp/us/eu) that you want to build an executable for, put an existing ROM at
`./baserom.<version>.z64` for asset extraction.

### Navigate to the sm64ex root directory.

### Run `make`. To turn certain features on and off, append any needed [build flags](https://github.com/sm64pc/sm64pc/wiki/Build-options) to your `make` invocation like so:

```
make EXTERNAL_DATA=1
```