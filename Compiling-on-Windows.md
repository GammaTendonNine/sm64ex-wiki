## Set up MSYS2, following [this guide](https://github.com/orlp/dev-on-windows/wiki/Installing-GCC--&-MSYS2).

## Install dependencies
```
pacman -S mingw-w64-i686-glew mingw-w64-x86_64-glew mingw-w64-i686-SDL2 mingw-w64-x86_64-SDL2 python3
```
## Copy baserom(s) for asset extraction

For each version (jp/us/eu) that you want to build an executable for, put an existing ROM at
`./baserom.<version>.z64` for asset extraction.

## On MSYS2, navigate to the sm64pc folder and then enter `./tools/audiofile-0.3.6/`. Inside this directory, run
```
autoreconf -i
```

Only leave this directory on step 9.

## Run the `configure` script
```
PATH=/mingw64/bin:/mingw32/bin:$PATH LIBS=-lstdc++ ./configure --disable-docs
```
## Run the `make` script
```
PATH=/mingw64/bin:/mingw32/bin:$PATH make
```
## Create a lib directory in `tools/`
```
mkdir ../lib
```

## Copy the compiled libaudiofile to `tools/lib/`
```
cp libaudiofile/.libs/libaudiofile.a ../lib/
cp libaudiofile/.libs/libaudiofile.la ../lib/
```

## Navigate back to `tools/`, then alter the `Makefile` and add `-lstdc++` on the following line
```
tabledesign_CFLAGS := -Wno-uninitialized -laudiofile -lstdc++
```

## Run `make`
```
PATH=/mingw64/bin:/mingw32/bin:$PATH make
```

## Navigate back to the sm64pc root directory.

## Finally, run `make` once more. 

(Note that mingw32 and mingw64 have been swapped. This is so you can build the 32bit application successfully.)

```
PATH=/mingw32/bin:/mingw64/bin:$PATH make
```