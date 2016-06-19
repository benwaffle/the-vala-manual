

Application entry point
=======================

All Vala applications are executed beginning with a method called
"main". This must be a non-instance method, but may exist inside a namespace or class. If the method takes a string array parameter, it will be passed the arguments given to the program on execution. If it returns an int type, this value will be passed to the user on the program's normal termination. The entry point method may not accept any other parameters, or return any other types, making the acceptable definitions:

\`\`\`vala void main() { ... }

int main() { ... }

void main(string[] args) { ... }

int main(string[] args) { ... }

\`\`\`

The entry point can be implicit, in the sense that you can write the main code block directly in the file outside the `main` function.

Back to [Vala Reference Manual](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual#)



Concepts
--------

This pages describes concepts that are widely applicable in Vala.
Specific syntax is not described here, see the linked pages for more details.


