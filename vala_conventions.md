# Vala Conventions

The logical structure of a Vala project is entirely based on the program text, not the file layout or naming. Vala therefore does not force particular naming schemes or file layouts. There are established conventions derived from how GNOME related applications are normally written, which are strongly encouraged. The choice of directory structure for a project is outside the scope of this documentation.

Vala source files usually contain one main public class, after which the source file is named. A common choice is to convert this main class' name to lowercase, and prefix with its namespace, also in lower case, to form the file name. In a small project the namespace may be redundant and so excluded. None of this is a requirement, it is just a convention.

It is not encouraged to include declarations in more than one namespace in a single Vala source file, simply for reasons of clarity. A namespace may be divided over any number of source files, but will normally not be used outside of one project. Each library or application will normally have one main namespace, with potentially others nested within.

In source code, the following naming conventions are normally followed:

-   Namespaces are named in camel case: NameSpaceName

-   Classes are named in camel case: ClassName

-   Method names are all lowercase and use underscores to separate words: method\_name

-   Constants (and values of enumerated types) are all uppercase, with underscores between words: CONSTANT\_NAME

Vala supports the notion of a package to conveniently divide program sections. A package is either a combination of an installed system library and its Vala binding, or else is a local directory that can be treated in a similar way. In the latter case it will contain all functionality related to some topic, the scope of which is up to the developer. All source files in package are placed within a directory named for package name. For details on using packages, see the Vala compiler documentation