

Specifiers
==========

Specifiers always use the C name for whatever it is you are modifying.

For example if your namespace is *Foo* , and the Vala name for the type is *Bar* , then you would use `FooBar` .

Specifiers may also use wildcards, and all items that partially match the specifier will be selected. For example:

    *.klass hidden="1"

will hide the *klass* field in all types.

