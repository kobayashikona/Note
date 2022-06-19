# Installation and Setup

## installing the c++ compiler on windows

If we want to check whether we install the compiler correctly, we just need to type `cmd` in command line so as to open a command promopt window.Then,we should type `g++ --version` and press 'enter'.Our operation is right if we get something like the version of g++ on the window.

## using command-line interface on windows

- **open command-line interface** :press win+r,and type `cmd`.
- **switch drive letter**:type the drive letter you want to go to and `:`.
- **go to subfolder**:type `cd `(p.s. there is a space behind cd) and the subfolder you want to go to.
- **go back to upper-level folder**:type `cd ..`(p.s. there is one space behind cd).
- **list files in current directory**:type`dir`.
- **compile source file**:type`g++ -Wall -std=c++11 test.cpp -o test`,`g++` means the compiler we choose,`-Wall` turns on all compiler warnings,`-std=c++11` decides the standard of language we choose,`test.cpp` is the source file to compile,`-o test` is of no necessity,while we can formulate name of the executive program in this way.

## using command-line interface on Linux(ubuntu)

- **check the workspace**:type `pwd`.
- **go to subfolder**:type `cd `(p.s. there is a space behind cd) and the subfolder you want to go to.
- **go back to upper-level folder**:type `cd ..`(p.s. there is one space behind cd).
- **list files in current directory**:type`ls`.
- **compile source file**:type`g++ -Wall -std=c++11 test.cpp -o test`,`g++` means the compiler we choose,`-Wall` turns on all compiler warnings,`-std=c++11` decides the standard of language we choose,`test.cpp` is the source file to compile,`-o test` is of no necessity,while we can formulate name of the executive program in this way.(**caution**:The extension of executive program on windows is `.exe` while it is `.out` on ubuntu) Sometimes,the command can be simplified to `g++ test.cpp` or `g++ test.cpp -o test.out` if you want to specify name of the executive program.
- **run the program**:type `./test.out` where `test.out` is the executive program we want to run and then we can get the output of the program.

## Building and Running C++ Programs with VSCode on Linux

1. Open a folder and create a `.cpp` file in it.
2. Go to 'command pallette' option under 'View' column, then type `C++` and find 'C/C++:Edit Configurations(UI)', select that.
3. Go to 'Compiler path' and change `gcc` to `g++`.
4. Come down to the 'C++ standard' and change to the c++ version we want to use. After that we will get a folder named '.vscode' and contain a 'c_cpp_properties.json' file.
5. Come to 'Terminal' and select 'Configuration Default Build Task and Run', then select 'g++' option.
6. Come to line 9 in the args section and add the following commands right agter that'-g'.
    ```c++
    "-Wall",
    "-std=c++17",
    ```
7. Change `{file}` in args section to `{fileFirname}/*.cpp`

## Debugging C++ Program with VSCode on Linux

### Configuration of the Debugger

1. Come to 'Run' and select 'Add Configuration'.
2. Select 'C++(GDB/LLDB)' and then selest 'g++'.
3. Modify the file called 'launch.json' which was just created, change the the entry for 'cwd' on line 14 from 'workspaceFolder' to 'fileDirname', save and close.

### The Progress of Dubugging
1. Select the file we want to debug and click "run and dubug" icon on the left.
2. Set breakpoints in your code and we can manage them in the lower left corner.
3. Click the little green run icon in the upper left corner.
    - the value of varibles will be shown on the left part.
    - the code in orange bar has not been executed.