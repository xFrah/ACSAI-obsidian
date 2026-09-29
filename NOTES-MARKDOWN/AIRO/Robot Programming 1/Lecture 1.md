don't use unicode (?)

Understand what the fuck is a c++ template.

ROS is publish-subscribe-like protocol (exactly like mqtt)

https://gitlab.com/grisetti/robotprogramming_2026_27


Impara i tipi di file in c++.

"3 minutes of compiling you want to shoot yourself."

Compiler will translate stuff into symbols, which are unresolved.
The linker takes the individual files and binds them, by resolving symbols pointers between each file.

g++ -o links (and compiles if needed) all files in the command line.

Makefile si genera da solo?
-l linka librerie

pkg-config 

cmake crea i makefiles in maniera semplice, non compila.
Basically makefile tells compiler what to build, cmake makes makefile, then you call make to compile stuff based on makefile.