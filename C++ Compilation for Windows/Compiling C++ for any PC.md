# Compiling C++ for any PC

The problem with publishing software compiled from C++ is that not every computer has the tools to run the executable. That's why it's important to test software you've written on a non-developer PC to see if everything works out of the box.

I ran into this problem myself creating CLCalc, which wouldn't run on a normal machine, throwing cryptic errors that I didn't understand. I did a bit of research and found the solution for this problem.

Usually, you compile a file with g++ with a command similar to the following:  
```powershell
g++ -o <programName> <programName>.cpp
```
This creates an executable that should always work on your computer. 

## Fixing the problem

To avoid the aforementioned problem, we must expand the compilation process by running the following commands:
```powershell
g++ -Wall -c -g <programName>.cpp -o obj\main.o
g++ -static -static-libgcc -static-libstdc++ -o "bin\<programName>.exe" obj\main.o
```
This way, all prerequisites for execution will be packed into this executable, making it work on any Windows PC (for all I know at least).
