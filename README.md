# Build
----
Requires [CMake 3.26](https://cmake.org/) and [vcpkg](https://github.com/microsoft/vcpkg)
#### Get VCPKG:
```ps
git clone https://github.com/microsoft/vcpkg
./vcpkg/bootstrap-vcpkg.bat
```
#### Make sure the following environment variables are set:
```
VCPKG_ROOT=[path_to_vcpkg]
VCPKG_DEFAULT_TRIPLET=x64-windows
```
#### Install dependencies 
```
./vcpkg install glm sdl2[alsa] sdl2-mixer[mpg123] sdl2-ttf sdl2-image lua sol2
```
  * For sdl2_mixer you name need to use:
```
./vcpkg install sdl2-mixer[mpg123] --recurse
```
* I tested this on ```Ubuntu 24``` and the build works. Just adjust default triplet for VCPKG to ```VCPKG_DEFAULT_TRIPLET=x64-linux```

#### Clone the repository 
```
git clone https://github.com/WizardBoyd/ZeldaClone.git
cd ZeldaClone
cmake -S . -B build
```
---- 
## Game Controls
| Key | Function  |  
| --- | ----------- | 
|  W  |  Move Up  | 
|  D  |  Move Right  | 
|  S  |  Move Down   | 
|  A  | Move Left   |
|  Q  | Pause Menu  |
| ESC |  Quit Game   | 
| RShift |  Sword Attack |
| SpaceBar |   Special Item |


* These are default keys that are now changable inside of the settings state. Changes the Action/Key/Btn Bindings.

## Game/Engine
This game/engine includes the following:
* An ECS (Entity Component System) to help manage entities, components, and systems that are in the game.
* #### A functioning Tilemap/Quest Editor that can create:
    * Tilemaps 
    * colliders
    * triggers (transport/secret areas/ traps/ etc.)
    * Uses Dear ImGui as the user interface
    * The Tilemap/Quest Editor still has some bugs; however, it does work

----
# Issues
There are still tonnes of issues in order to have a proper working game. 
* Needs proper AI for enemies.
* Player can still move after getting triforce.
* Titlescreen does not reset properly and will eventually crash.
