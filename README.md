# new-psx-project
Base PsyQ and Nugget project to download and modify.
- GDB server enabled and ready for VS Code attachment.
- Screen should turn purple when project is run.

---

## Setup
### Install the PsyQ Converted Libraries
1. ```cd``` to the project's root directory
2. ```wget http://psx.arthus.net/sdk/Psy-Q/psyq-4.7-converted-full.7z && 7z x psyq-4.7-converted-full.7z -o./psyq```
### Install MIPS Toolchain:
#### Debian (Ubuntu, Mint, Pop!\_OS...)
```sudo apt-get install gcc-mipsel-linux-gnu g++-mipsel-linux-gnu binutils-mipsel-linux-gnui```
#### Arch
On Arch derivatives (Manjaro), the mipsel environment can be installed from AUR : cross-mipsel-linux-gnu-binutils and cross-mipsel-linux-gnu-gcc using our AURhelper of choice:
```trizen -S cross-mipsel-linux-gnu-binutils cross-mipsel-linux-gnu-gcci```
### PCSX-Redux Emulator Setup:
#### Install:
[https://github.com/grumpycoders/pcsx-redux](https://github.com/grumpycoders/pcsx-redux)
#### PCSX-Redux Command Name:
- ```.vscode/launch.json``` starts the emulator using the command ```pcsx-redux```.
- Use the same command name or update ```.vscode/tasks.json``` for VS Code debugging.
### Test our setup
1. Type ```make``` in the terminal from the project's root directory
2. Run the executable with ```pcsx-redux -run -exe main.elf``` 

---

## Debugging
### Setup VS Code and Native Debug Extension
- Install the ```Native debug``` extension: [https://marketplace.visualstudio.com/items?itemName=webfreak.debug](https://marketplace.visualstudio.com/items?itemName=webfreak.debug)
- ```./vscode/launch.json``` contains our debug configs. Info: [https://pcsx-redux.consoledev.net/Debugging/gdb-server/](https://pcsx-redux.consoledev.net/Debugging/gdb-server/).
- Choose whether ```PCSX-Redux``` automatically starts alongside the debugger by switching VS Code debug configurations.
### PCSX-Redux Configuration
- GBD server and debugging are enabled automatically for ```PCSX-Redux``` using ```./pcsx.json```. Dynarec is disabled for CPU debugging. These settings and others are configured there.
### More Debugging Tools and Methods
- ```PCSX-Redux``` is capable of connecting to other GBD clients and has strong debugging capabilities. Info: [https://pcsx-redux.consoledev.net/Debugging/introduction/](https://pcsx-redux.consoledev.net/Debugging/introduction/)

