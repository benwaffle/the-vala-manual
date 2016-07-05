# Getting Started

The classic "Hello, world" example in Vala:

```vala
using GLib;

public class HelloWorld : Object {

    public static int main(string[] args) {
        stdout.printf("hello, world");
        return 0;
    } 
    
}
```

The source code for Vala programs are stored in one or more UTF-8 encoded text files with the extension ".vala", such as `hello.vala`. Simple programs like the one above can be compiled with a command like:

`valac hello.vala`

This will produce an executable file called `hello` which will produce the following output when run:

`hello, world`

Although simple, this program illustrates several key features of Vala.
* The `using GLib;` directive references the GLib namespace. Although this is redundant as the GLib namespace is automatically added to all Vala files, it is provided for clarity.
* The `main` method is a static member of the `HelloWorld` class. This means it is globally accessible through the class name rather than an instance.
* The entry point for a program, which is the first method called when it begins executing, is always called `main`. An alternative entry point can be specified but it must not be an instance member.

