# Vala syntax

Vala's syntax is modelled on C\#'s, and is similar to all C-like languages. Curly braces are the basic delimeter, marking the start and end of a declaration or block of code.

There is no whitespace requirement, though this is a standard format that is used in Vala itself, and in many Vala projects. This format is a version of the coding style used for glib and gnome projects. It is not fully described in this document, other than being used for all examples.

There is flexibility in the order of declarations in Vala. It is not required to pre-declare anything in order to use it.

Identifiers all follow the same rules, whether for local variables or class names. Legal identifiers must begin with one alphabetic character or underscore. This can be followed by any number of alphanumeric characters or the underscore (/[:alpha:\_]([:alphanum:\_])\*/). It is also possible to use language keywords as identifiers, provided they are prefixed with a "@". The "@" is not considered a part of the identifier. It simply informs the compiler that the following token should be considered as an identifier.