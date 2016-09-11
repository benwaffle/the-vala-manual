# Getting Started

The classic "Hello, world" example in Vala:

```vala
void main() {
    print ("hello, world!\n");
}
```

The source code for Vala programs are stored in one or more UTF-8 encoded text files with the extension ".vala", such as `hello.vala`. Simple programs like the one above can be compiled with a command like:

`valac hello.vala`

This will produce an executable file called `hello` which will produce the following output when run:

`hello, world`

The entry point for a program, which is the first method called when it begins executing, is always called `main`.
