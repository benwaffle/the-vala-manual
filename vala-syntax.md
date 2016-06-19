<div id="vala-syntax" class="section level1">

Vala syntax
===========

Vala's syntax is modelled on C\#'s, and is therefore similar to all
C-like languages. Curly braces are the basic delimeter, marking the
start and end of a declaration or block of code.

There is no whitespace requirement, though this is a standard format
that is used in Vala itself, and in many Vala projects. This format is a
version of the coding style used for glib and gnome projects, but is not
fully described in this document, other than being used for all
examples.

There is flexibility in the order of declarations in Vala. It is not
required to pre-declare anything in order to use it before its
declaration.

Identifiers all follow the same rules, whether for local variables or
class names. Legal identifiers must begin with one alphabetic character
or underscore, followed by any number (zero or more) of alphanumerics or
underscores (/[:alpha:\_]([:alphanum:_])\*/). It is also possible to use
language keywords as identifiers, provided they are prefixed with a "@"
when used in this way - the "@" is not considered a part of the
identifier, it simply informs the compiler that the token should be
considered as an identifier.

</div>
