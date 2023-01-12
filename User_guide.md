# ARP-ASSIGNMENT-2 Guide to Compile and run the project
GITHUB LINK OF THE PROJECT: https://github.com/PedroFigueroaS/FIRST_ASSIGNMENT_FIGUEROA_S5439029.git
In particular, the repository is organized as follows:
- The `src` folder contains the source code for the Master, Process A, and Process B.
- The `include` folder contains all the data structures and methods used within the ncurses framework to build the two GUIs. 
- The `bin` folder is where the executable files of the codes in the src files are stored

## ncurses installation
To install the ncurses library, simply open a terminal and type the following command:
```console
sudo apt-get install libncurses-dev
```
## litbitmap installation
Follow the step in the README.md file to install the litbitmap library.

## Compiling the project

In the main file, there is a shell executable called build.sh. This executable is run as follows:

```console
./build.sh
```
the content of this executable is the following code lines:
```console
#! /usr/bin/bash
gcc src/processA.c -lbmp -lm -lncurses -o bin/processA -lrt -pthread
gcc src/processB.c -lbmp -lm -lncurses -o bin/processB -lrt -pthread
gcc src/master.c -o bin/master -lrt
```
This shell code allows to compile all the processes involved in the simulation and also is a more efficient way to make modifications.

## Running the project

In the same address of the shell executable to compile the project, there is the other executable that allows running the project called run.sh. In a terminal, type the next command

```console
./run.sh
```
the content of this executable is the following code lines:

```console
clear
./bin/master
```
This shell code allows running the master code of the project, which executes the other process involved in the project, and clears the current terminal

To finish the process, in the terminal where the ./run.sh programm was run, use the Ctrl+C command to kill the master, and kill the other process


## Troubleshooting after launching the run executable

It is possible that after launching the run.sh for the first time, process A and/or process B may crash or not work. In this case, follow the next steps:

1. run the ./build.sh command first, to compile and create the executables
2. run the ./run.sh command after that, to run the simulation
3. Try to rescale the size of both consoles to become 80x30, to avoid crashing the program while trying to reach a position outside the limits of the code.



