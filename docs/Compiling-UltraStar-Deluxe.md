[Freepascal](http://freepascal.org/) 3.0.0 or newer is required to compile UltraStar Deluxe. If you had some older version of fpc installed before, make sure to remove everything of it correctly before trying to install freepascal (otherwise compiling will fail with various weird error messages). Also, using the 3.0-development branch with current fixes is suggested.
If you want to help the project by coding patches, we suggest you to use the [Lazarus 1.6](http://www.lazarus-ide.org/) or newer integrated development environment.
For linking and running the game, the following libraries are also required:
- SDL2, SDL2_gfx, SDL2_mixer, SDL2_image, SDL2_ttf, SDL2_net
- ffmpeg 2.8 or older
- sqlite
- [bass](http://www.un4seen.com/bass.html)
- some fonts like ttf-dejavu and ttf-freefont
- portaudio
- pcre
- lua 5.1 or 5.2 or 5.3
- opencv if you want webcam support
- projectM if you want audio visualisation support

####Compiling using Lazarus
1. Start Lazarus.
2. Choose Project → Open Project … in the menu bar. A file-dialog box will show.
3. Change to the src subdirectory of your USDX working copy (e.g. ultrastardx/src).
  * If you are running Windows, open the ultrastardx-win.lpi project-file.
  * On Unix-like systems use the ultrastardx-unix.lpi file.
4. Now you can compile USDX by choosing the menu entry Run → Build or pressing Ctrl+F9.
8. If you want to compile and/or start USDX directly choose Run → Run or press F9.

####Compiling on Linux/BSD using make
1. make sure all required libraries are installed 
  * for current debian / ubuntu: 
    `sudo apt-get update && sudo apt-get install git fpc libsdl2-dev libsdl2-image-dev libsdl2-image-2.0-0 libsdl2-2.0-0 libsdl2-mixer-2.0-0 libsdl2-mixer-dev libsdl2-net-2.0-0 libsdl2-net-dev libsdl2-ttf-2.0-0 libsdl2-ttf-dev libsdl2-gfx-1.0-0 libsdl2-gfx-dev ffmpeg libavdevice-dev libsqlite3-0 libsqlite3-dev libpcre3 libpcre3-dev ttf-dejavu ttf-freefont portaudio19-dev lua5.1-dev libpng16-16 libopencv-highgui-dev libprojectm-dev`
  * for arch linux there is an aur package called [ultrastardx-git](https://aur.archlinux.org/packages/ultrastardx-git)
2. `git clone https://github.com/UltraStar-Deluxe/USDX`
2. `cd USDX`
3. `./configure` (or use _autoconf_)
4. `make`
6. Play the game, 
   * install the game and start it
     - `sudo make install`
     - `ultrastardx`
   * or start it directly  
     `./game/ultrastardx`

####Compiling on OS X
- USDX is built using _Homebrew_ and official _FreePascal build_ (using its compiler _FPC_)
- You can install Homebrew from [brew.sh](http://brew.sh)
- You can get the FPC build from [freepascal.org](http://www.freepascal.org/down/i386/macosx.var)
- Don't miss _XQuartz_ from [xquartz.org](http://www.xquartz.org)
- Make sure the XCode command line tools are installed. `xcode-select --install`
- Needed brew libraries can be installed using:
  * `brew install sdl2 sdl2_gfx sdl2_image sdl2_mixer sdl2_net sdl2_ttf ffmpeg libav portaudio binutils sqlite freetype libpng pcre lua libtiff`
  * `brew switch ffmpeg 2.8.6`
- Pass argument `--enable-osx-fink` or `--enable-osx-brew` (default) according to the packaging you are using
- `./configure`
- `make macosx-standalone-app`

Feel free to fork this project, modify it to your hearts content and maybe also do pull requests to this repository for additional features, improvements or clean-ups.