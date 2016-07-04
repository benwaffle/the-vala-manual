

Signals
=======

> **Note**
> Signals are only available to GObject derived classes.

Signals are a system allowing a classed-type instance to emit events which can be recieved by arbitrary listeners. Receiving these events is achieved by connecting the signal to a handler, for which Vala has a specific syntax. Signals are integrated with the GLib [MainLoop](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/MainLoop#) system, which provides a system for queueing events (i.e. signal emissions,) when needed - though this capability is not needed in non-threaded applications.

-   class-instance-signal-declaration:

    -   [ class-member-visibility-modifier ] [ class-method-type-modifier ] **signal** return-type signal-name **(** [ params-list ] **)** **;**


-   signal-name:

    -   identifier

Signals may also provide an extra piece of information called a signal detail. This is a single string, which can be used as an initial hint as to the purpose of the signal emission. In Vala you can register that a signal handler should only be invoked when the signal detail matches a given string.

A typical use of signal details is in GObject's own "notify" signal, which says that a property of an object has changed - GObject uses the detail string to say which property has been changed.

To assign a handler to a signal, (or register to receive this type of event from the instance), use the following form of expression:

-   signal-connection-expression:

    -   qualified-signal-name [ signal-detail ] **.connect(** signal-handler **);**


-   qualified-signal-name:

    -   [ qualified-namespace-name **.** ] variable-identifier **.** signal-name


-   signal-detail:

    -   **[\*\* expression \*\*]**


-   signal-handler:

    -   expression

    -   qualified-method-name

    -   lambda-expression

This expression will request that the signal handler given be invoked whenever the signal is emitted. In order for such a connection expression to be legal, the handler must have the correct signature. The handler should be defined to accept as parameters the same types as the signal, but with an extra parameter before. This parameter should have the type of the class in which the signal is declared. When a signal is emitted all handlers are called with this parameter being the object by which the signal was emitted.

The time that an arbtirary expression is acceptable in this expression is when that expression evaluates to an instance of a delegate type, i.e. to a method that is a legal handler for the signal. For details on delegates, see [Delegates](delegates.md). For details on lambda expressions see [Methods/Lambdas](lambdas.md).

Note that optional signal detail should be directly appended to the signal name, with no white space, e.g. `o.notify["name"] += ...`

It is also possible to disconnect a signal handler using the following expression form:

-   signal-disconnection-expression:

    -   qualified-signal-name [ signal-detail ] **-=** connected-signal-handler


-   connected-signal-handler:

    -   expression

    -   qualified-method-name

Note that you cannot disconnect a signal handler which was defined inline as a lambda expression and then immediately connected to the signal. If this is the effect you really need to achieve, you must assign the lambda expression to an identifier first, so that the lambda can be referred to again at a later time.
