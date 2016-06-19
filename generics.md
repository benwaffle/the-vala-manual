Generics
--------

Generic programming is a way of defining that something is applicable to a variety of potential types, without having to know these types before hand. The classic example would be a collection such as a list, which can be trivially customised to contain any type of data elements. Generics allow a Vala programmer to have these customisations done automatically.

Some of these are possible, which?

-   class Wrapper \< T \> : Object { ... }

    new Wrapper \< Object \> ( ) ;

    BUG: class StringWrapper : Wrapper \< string \> ( ) { ... }

    FAIL: class WrapperWrapper \< Wrapper \< T \> \> : Object { ... }

    FAIL: new WrapperWrapper \< Wrapper \< Object \> \> ( ) ;

    interface IWrapper \< T \> { ... }

    class ImpWrapper1 \< T \> : Object, IWrapper \< T \> { ... }

    BUG: class ImpWrapper2 : Object, IWrapper \< string \> { ... }


