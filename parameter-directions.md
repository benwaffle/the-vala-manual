

Parameter directions
====================

The basics of method parameter semantics are described on the concepts page (see [Concepts/Variables, fields and parameters](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#Variables,_fields_and_parameters)
). This basic form of parameter is technically an "in" parameter, which is used to pass data needed for the method to operate. If the parameter is of a reference type, the method may change the fields of the type instance it receives, but assignments to the parameter itself will not be visible to the invoking code. If the parameter is of a value type,
which is not a fundamental type, the same rules apply as for a reference type. If the parameter is of a fundamental type, then the parameter will contain a copy of the value, and no changes made to it will be visible to the invoking code.

If the method wishes to return more than one value to the invoker, it should use "out" parameters. Out parameters do not pass any data to the method - instead the method may assign a value to the parameter that will be visible to the invoking code after the method has executed,
stored in the variable passed to the method. If a method is invoked passing a variable which has already been assigned to as an out parameter, then the value of that variable will be dereferenced or freed as appropriate. If the method does not assign a value to the parameter,
then the invoker's variable will end with a value of "null".

The third parameter type is a "ref" argument (equivalent to "inout" in some other languages.) This allows the method to receive data from the invoker, and also to assign another value to the parameter in a way that will be visible to the invoker. This functions similarly to "out"
parameters, except that if the method does not assign to the parameter,
the same value is left in the invoker's variable.

