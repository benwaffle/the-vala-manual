# Overview

Vala is a programming language that aims to bring modern language features to GNOME developers. It does this without imposing any extra runtime requirements or using a different ABI than applications and libraries written in C. It provides a concise way of using GLib and GObject features, but does not attempt to expose all possibilities. In particular, Vala is primarily a statically typed language by design.

The syntax of Vala is like C#, with some modifications to better fit the GObject type system. Vala supports modern language features as the following:

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

The only support that Vala applications require at runtime are the standard GLib and GObject libraries. It is possible to use any system library from Vala, provided that a VAPI file is written to describe its interface. Vala is distributed with VAPI descriptions for most of the GNOME libraries and lots of others as well.

Vala provides easy integration with DBus. It automatically creates boiler plate code for exposing objects, dispatching methods and other tasks.