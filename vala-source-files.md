<div id="vala-source-files" class="section level1">

Vala source files
=================

There are two types of Vala input files. Vala source files (with a
".vala" extension) contain compileable Vala code. VAPI files (with a
".vapi" extension) describe an interface to a library, which can be
written in either Vala or C. VAPI files are not compileable, and cannot
contain any executable code - they are used when compiling Vala source
files.

There are no requirements for how Vala source files are named, although
there are conventions that can be followed. VAPI files are usually named
to matched the pkg-config name of the library they relate to; they are
described more fully in the documention about bindings. All Vala input
files should be encoded in UTF-8.

</div>
