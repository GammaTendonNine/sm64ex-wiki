Contributor [Hyenadae](https://github.com/Hyenadae/) has developed a script that guides through the complete building process on RPis. The script's steps are as follows:
  
  * Installs dependencies;
  * Helps enabling VC4_DRM on RPis 0 to 3;
  * Makes memory adjustments on RPis 0 and 1 to guarantee that compilation doesn't break;
  * Allows installation modified SDL2 with KMS, which removes the need of X11 and guarantees the highest performance of any RPi running VC4;
  * Clones sm64pc if the script is not inside a folder with the necessary files;
  * Checks for assets and the existence of the baserom.*.z64;
  * Compiles sm64pc.

The script is included on the master branch but can be downloaded [here](https://raw.githubusercontent.com/sm64pc/sm64pc/master/pisetup.sh).