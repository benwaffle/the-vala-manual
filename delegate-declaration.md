

Delegate declaration
====================

The syntax for declaring a delegate changes slightly based on what sort of delegate is being declared. This section shows the form for a namespace delegate. Many of the parts of the declaration are common to all types, so sections from here are referenced from class delegates,
interface delegates, etc.

-   delegate-declaration:

    -   instance-delegate-declaration

    -   static-delegate-declaration

-   instance-delegate-declaration:

    -   [ access-modifier ] **delegate** return-type qualified-delegate-name **(** method-params-list **)** [ **throws** error-list ] **;**


-   static-delegate-declaration:

    -   [ access-modifier ] **static** **delegate** return-type qualified-delegate-name **(** method-params-list **)** [ **throws** error-list ] **;**


-   qualified-delegate-name:

    -   [ qualified-namespace-name **.** ] delegate-name


-   delegate-name:

    -   identifier

Parts of this syntax are based on the respective sections of the method declaration syntax (see
[Methods](methods.md) for details).
