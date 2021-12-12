# CHIP-8 EMULATOR

This is a simple Chip-8 emulator written in C++ using SDL2 library.  
Majority of the code has been reused from [Austin Morlan's guide](https://austinmorlan.com/posts/chip8_emulator/).  
This is my first attempt of building an emulator.  

### Dependency

The program requires [SDL2](https://www.libsdl.org/) library to work.  
Install it before compiling the source code.  

### How to install

To compile the program from source Cmake has to be installed.  

1. Clone the repository or download & extract the compressed file.  
2. Open the folder.  
3. Run the following commands.  
```zsh
cmake -S . -B build -D CMAKE_BUILD_TYPE=Release
cd build
sudo make install
```

### How to use

Running the program is pretty straight forward.  
It requires Chip-8 compatible ROM Files.  
To load the ROM file run:
```zsh
./chip8 <Scale> <Delay> <ROM>
# Example: ./chip8 10 1 Test.ch8
```
