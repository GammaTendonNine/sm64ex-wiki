### Set up MSYS2.

Download the newest version of the MSYS2 installer from [here](https://github.com/msys2/msys2-installer/releases) and install it.

Run the `MINGW64` prompt if you wish to build a 64-bit version of the executable, or the `MINGW32` prompt otherwise.

Enter `pacman -Syuu` in the prompt and hit Enter. Press `Y` when it asks if you want to update packages. If it asks you to close the prompt, do so, then restart it and run the same command again. This updates the packages to their latest versions.

### Install dependencies.

Enter this command to install packages necessary to build sm64ex:

```
pacman -S unzip make git mingw-w64-i686-gcc mingw-w64-x86_64-gcc mingw-w64-i686-glew mingw-w64-x86_64-glew mingw-w64-i686-SDL2 mingw-w64-x86_64-SDL2 python3
```

### Obtain the source code.

```
git clone https://github.com/sm64pc/sm64ex.git -b nightly
cd sm64ex
```

### Copy baserom(s) for asset extraction.

For each version (jp/us/eu) that you want to build an executable for, put an existing ROM at
`./baserom.<version>.z64` for asset extraction.

For example, if you want to build the US version, there should be a ROM file called `baserom.us.z64` in the sm64ex directory (meaning next to the Makefile).

If during the build process you get messages saying that the ROM has an incorrect hash, there is a possibility that it's a V64 ROM that needs to be byteswapped. To do that, use [this web tool](https://hack64.net/tools/swapper.php).

### Run `make`. To turn certain features on and off, append any needed [build flags](https://github.com/sm64pc/sm64pc/wiki/Build-options) to your `make` invocation like so:

```
make EXTERNAL_DATA=1
```