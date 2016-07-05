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
* The `using GLib;` directive references the GLib namespace[^1]. The GLib namespace contains the `Object` class and `stdout` instance used to output text to the console. Namespaces provide a convenient means of organizaing the source code of multiple programs and libraries. The `using` directive allows the use of unqualified names for members of the specified namespace. Without the using directive, the full qualified name would need to be used - i.e. `GLib.Object`.
* The `main` method is a static member of the `HelloWorld` class. This means it is globally accessible through the class name rather than an instance.
* The entry point for a program, which is the first method called when it begins executing, is always called `main`. An alternative entry point can be specified but it must not be an instance member.




[^1]: This is redundant as the GLib namespace is automatically added to all Vala files but is provided for explanatory purposes.