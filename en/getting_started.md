# Getting Started

The classic "Hello, world" example in Vala:

```vala
public class HelloWorld : Object {

    public static int main(string[] args) {
        stdout.printf("hello, world");
        return 0;
    } 
    
}
```

The source code for Vala programs are stored in one or more UTF-8 encoded text files with the extension ".vala", such as `hello.vala`. Simple programs like the one above can be compiled with a command like:

`valac -o hello hello.vala`

This will produce an executable file called `hello`. `valac` is the Vala compiler. It allows you to take more control of the compilation and linking processes, which is outside the scope of this introductory section.
