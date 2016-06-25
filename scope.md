

Scope
=====

The execution of a method happens in a scope created for each invocation, which ceases to exist after execution is complete. The parent scope of this transient scope is always the scope the method was declared in, regardless of where it is invoked from.

Parameters and local variables exist in the invocation's transient scope. For more on scoping see [Concepts/Scope and naming](scope-and-naming.md).

