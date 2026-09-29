Every time you write a header file, start with # pragma once, this is to have a singleton of this while compiling, else it will expand in each file its imported in.

Basic types:
- char 1 byte char
- in 4 byte
- long int 8 byte
- float 4 byte
- double 8 byte

Qualifiers:
- const: cant be changed
- unsigned
- long makes int 64 bit
- short makes int 16 bit
- static multiple meanings depending on context

Addresses:
- int * b = address of an int
- &a = get address of a
- ** pointer of a pointer

"In c++ we have a number of operators that is disgusting."

If we do not use the & operator, stuff is deepcopied.

stack = local variables
heap = static variables

heap variables do not disappear even if you exit the scope. so you need to keep thrack of them carefully.

new keyword creates a struct or array or any type i guess and returns its pointer.

delete keyword is used for deleting this stuff.

Structs can have functions

structs can have constructors, constructors with arguments.

there is also a copy constructor but i don't understand what it is, also a destructor.

![[Pasted image 20260925123228.png]]

understand why constructors can be called from other constructors while opening a block.