# Vala Source Files

There are two types of Vala input files. Vala source files (with a ".vala" or a ".gs" extension) contain compilable Vala code. VAPI files (with a ".vapi" extension) describe an interface to a library, which may have been written in Vala or C. VAPI files are not compilable, and cannot contain any executable code. They are only used when compiling Vala source files.

There are no requirements for how Vala source files are named, although there are conventions that can be followed. VAPI files are usually named to matched the pkg-config name of the library they relate to. They are more fully described in the documentation about bindings. 
All Vala input files must be UTF-8 encoded.
