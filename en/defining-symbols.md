

Defining symbols
================

It's not possible to define a preprocessor symbol inside the Vala code (like with C). The only way to define a symbol is to pass it to `valac` with the option `-D` .

```sh
$ valac -D FOOBAR main.vala
$ valac -D FOO -D BAR main.vala
```
