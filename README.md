Makefile
========

Basic generic Makefile for building C project. This avoid wasting hours to create new Makefile
for every new project. Edit setting inside Makefile file, fill the source tree with your source
code and Makefile should be able to build your program.


## Target
Name  | Description
------|------------
all   | Build the program.
run   | Run the program.
clean | Remove generated program and other temporary file.
dist  | Create zip file containing current project after clean is run.


## Features
* Recusively search all source files in the source directory and compile them.
* Generate header file dependencies to recompile source files when header file are changed.
* Build in quiet mode unless VERBOSE=true option is set. It only list action being performed by default.
* Separate source file and build file to keep the development environment clean.


## Future work
* Add Makefile for C++ Project.
* Add a way to generate build folder automatically
* Add doc target to generate documentation using doxygen
* Add check target to run test on the build program (still have to think on how to handle this).


## Authors
* Aurelien Tran (aurelien.tran@gmail.com)

