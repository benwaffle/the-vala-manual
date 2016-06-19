# Vala Compilation

Vala programs and libraries are translated into C before being compiled into machine code. This stage is intended to be entirely transparent unless you request otherwise, as such it is not often required to know the details.

When performing a more complicated compile or link process than valac's default, valac can be instructed to simply output its intermediate C form of the program and exit. Each Vala source file is transformed into a C header and a C source file, each having the same name as the Vala source file except for the extension. These C files can be compiled without any help from any Vala utility or library.

The only times it is definitely required to be aware of the translation process is when a Vala feature cannot be represented in C, and so the generated C API will not be the same as the Vala one. For example, private struct members are meaningless in C. These issues are indicated in this documentation.
