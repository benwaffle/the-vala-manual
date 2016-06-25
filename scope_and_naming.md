# Scope and naming

A "scope" in Vala refers to any context in which identifiers can be valid. Identifiers in this case refers to anything named, including class definitions, fields, variables, etc. Within a particular scope, identifiers defined in this scope can be used directly:

```vala
void main() {
	int a = 5;
	int b = a + 1;
}
```

Scopes in Vala are introduced in various ways.

-   Named scopes can be created directly with declarations like namespaces. These are always in existence when the program is running, and can be referred to by their name.

-   Transient scopes are created automatically as the program executes. Every time a new code block is entered, a new scope is created. For example, a new scope is created when a method is invoked. There is no way to refer to this type of scope from outside.

-   Instance scopes are created when a data type is instantiated, for example when a new instance of a classed type is created. These scopes can be accessed via identifiers defined in other scopes, e.g. a variable to which the new instance is assigned.

To refer to an identifier in another scope, you must generally qualify the name. For named scopes, the scope name is used; for instance scopes, any identifier to which the instance is assigned can be used. See [Expressions/Member access expressions](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Expressions#Member_access_expressions) for the syntax of accessing other scopes.

Scopes have parent scopes. If an identifier is not recognised in the current scope, the parent scope is searched. This continues up to the global scope. The parent scope of any scope is inferred from its position in the program. The parent scope can easily be identified as it is the scope the current declaration is in.

For example, a namespace method creates a transient scope when it is invoked. The parent of this scope is the namespace which contains the definition of the method. There are slightly different rules applied when instances are involved, as described at [Classes/Class scope](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#Class_scope).

The ultimate parent of all other scopes is the global scope. The scope contains the fundamental data types, e.g. int, float, string. If a program has a declaration outside of any other, it is placed in this scope.

#### Qualifying names

The following rules describe when to qualify names:

-   For names in the same scope as the current definition, just the name should be used.

-   For names in scopes of which the current is parent, qualify with just the names of scopes that the current definition is not nested within.

-   For names in other scopes entirely, or that are less deeply nested than the current, use the fully qualified name (starting from the global scope.)

There are some intricacies of scopes described elsewhere in this documentation. See [Classes](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#) for how scopes are managed for inherited classes.

Vala will lookup names assuming first that they are not fully qualified. If a fully qualified name can be partially matched locally, or in a parent scope that is not the global scope, the compilation will fail. To avoid problems with this, do not reuse names from the global scope in other scopes.

There is one special scope qualifier that can be used to avoid the problem described in the previous paragraph. Prefixing an identifier with `global::` will instruct the compiler to only attempt to find the identifier in the global scope, skipping all earlier searching.