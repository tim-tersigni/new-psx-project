# new-psx-project
## About
My base PsyQ and Nugget project to create new projects with.
- Configured to debug using ```PCSX-Redux```'s GDB server and VS Code with the Native Debug extension.
- Based on [https://github.com/ABelliqueux/nolibgs_hello_worlds](https://github.com/ABelliqueux/nolibgs_hello_worlds) and Lameguy64's Hello World.

---

## Setup
### [Download](https://github.com/tim-tersigni/new-psx-project/archive/refs/heads/main.zip) and Unzip the Project
#### Bash command to download and unzip
```
wget -O new-psx-project.zip https://github.com/tim-tersigni/new-psx-project/archive/refs/heads/main.zip && 
unzip new-psx-project.zip && 
rm new-psx-project.zip && 
mv new-psx-project-main new-psx-project
```
### Install PsyQ Converted Libraries
1. ```cd``` to the project's root directory.
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
#### Set PCSX-Redux Command Name:
- Ensure ```PCSX-Redux``` can be launched with ```pcsx-redux -stdout``` from the terminal.
- If not, update ```.vscode/tasks.json``` or the included debug config will not work.
### Test your setup
1. Type ```make``` in the terminal from the project's root directory.
2. Run the executable with ```pcsx-redux -run -exe main.elf```.
3. The emulator should display purple when project is run.
---

## Debugging
### Setup VS Code and Native Debug Extension
- Install the ```Native debug``` extension: [https://marketplace.visualstudio.com/items?itemName=webfreak.debug](https://marketplace.visualstudio.com/items?itemName=webfreak.debug).
- ```./vscode/launch.json``` contains our debug configs. Info: [https://pcsx-redux.consoledev.net/Debugging/gdb-server/](https://pcsx-redux.consoledev.net/Debugging/gdb-server/).
- Choose whether ```PCSX-Redux``` automatically starts alongside the debugger by switching VS Code debug configurations.
### PCSX-Redux Configuration
- GBD server and debugging are enabled automatically for ```PCSX-Redux``` using ```./pcsx.json```. Dynarec is disabled for CPU debugging. These settings and others are configured there.
### More Debugging Tools and Methods
- ```PCSX-Redux``` is capable of connecting to other GBD clients and has strong debugging capabilities. Info: [https://pcsx-redux.consoledev.net/Debugging/introduction/](https://pcsx-redux.consoledev.net/Debugging/introduction/).

