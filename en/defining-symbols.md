

Defining symbols
================

It's not possible to define a preprocessor symbol inside the Vala code (like with C). The only way to define a symbol is to pass it to `valac` with the option `-D` .

```bash
$ valac -D FOOBAR conditional-compilation.vala
$ ./conditional-compilation
$ valac -D FOO -D BAR conditional-compilation.vala
$ ./conditional-compilation
$ valac -D FOO -D BAR -D FOOBAR -D NOFOO conditional-compilation.vala
$ ./conditional-compilation
```
