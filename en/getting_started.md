# Getting Started

The classic "Hello, world" example in Vala:

```vala
int main(string[] args) {
  stdout.printf("hello, world");
  return 0;
}       
```

Store the code in a file whose name ends in ".vala", such as `hello.vala` , and compile it with the command:

`valac -o hello hello.vala`

This will produce an executable file called `hello` . "valac" is the Vala compiler. It allows you to take more control of the compilation and linking processes, which is outside the scope of this introductory section.
