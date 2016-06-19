# Overview

Vala is a programming language that aims to bring modern language features to GNOME developers without imposing any additional runtime requirements and without using a different ABI than applications and libraries written in C. It provides a concise way of using GLib and
GObject features, but does not attempt to expose all possibilities. In particular, Vala is primarily a statically typed language - this is a design decision, not an oversight.

The syntax of Vala is similar to C#, modified to better fit the GObject type system. Vala supports modern language features as the following:

 * Interfaces
 * Properties
 * Signals
 * Foreach
 * Lambda expressions
 * Type inference for local variables
 * Generics
 * Non-null types
 * Assisted memory management
 * Exception handling
 * Type modules (Plugins)

Vala is designed to allow access to existing C libraries, especially GObject-based libraries, without the need for runtime bindings. All that is needed to use a library with Vala is an API file, containing the class and method declarations in Vala syntax. Vala currently comes with bindings for GLib and GTK+ and many others from the GNOME Platform.

Using classes and methods written in Vala from an application written in C is not difficult. The Vala library only has to install the generated header files and C applications may then access the GObject-based API of the Vala library as usual. It should also be easily possible to write a bindings generator for access to Vala libraries from applications written in e.g. C# as the Vala parser is written as a library, so that all compile-time information is available when generating a binding.


The only support that Vala applications require at runtime are the standard GLib and GObject libraries. It is possible to use any system library from Vala, provided that a VAPI file is written to describe the interface - Vala is distributed with VAPI descriptions of most libraries commonly used by GNOME applications, and many others as well.

Vala provides easy integration with DBus, by automatically writing boiler plate code where required, for exposing objects, dispatching methods, etc.