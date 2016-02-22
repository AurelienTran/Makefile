Makefile
========

Basic generic Makefile for building C project. This avoid wasting hours to create new Makefile
for every new project. Edit setting inside Makefile file, fill the source tree with your source
code and Makefile should be able to build your program.

## Features:
* Recusively search all source files in the source directory and compile them.
* Generate header file dependencies to recompile source files when header file are changed.
* Unless VERBOSE=true option is set, builds in quiet mode (list only actions being performed).

## Future work:
* Add dist target to generate zip file containing the project.

## Authors:
* Aurelien Tran (aurelien.tran@gmail.com)

