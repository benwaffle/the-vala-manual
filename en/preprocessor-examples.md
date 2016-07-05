# Examples
This example shows using preprocessor directives for conditional compilation.

```vala
void main () {

#if ( FOOBAR || FOO || BAR ) && (FOOBAR == FOO && FOO == BAR)
    message ("FOOBAR == FOO == BAR");
#endif

#if ! NOFOO && (FOOBAR || (FOO && BAR)) 
    message ("FOOBAR");
#elif FOO && ! NOFOO 
    message ("FOO");
#elif BAR && ! NOFOO
    message ("BAR");
#elif NOFOO
#if FOOBAR || (FOO && BAR)
    message ("NOFOO FOOBAR");
#else
    message ("NOFOO");
#endif
#else
    message ("Nothing relevant defined");
#endif

}
```
Compile and Run
```
$ valac -D FOOBAR conditional-compilation.vala
$ ./conditional-compilation
$ valac -D FOO -D BAR conditional-compilation.vala
$ ./conditional-compilation
$ valac -D FOO -D BAR -D FOOBAR -D NOFOO conditional-compilation.vala
$ ./conditional-compilation
```