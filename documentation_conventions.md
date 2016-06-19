# Documentation Conventions
A large amount of this documentation describes the language features precisely using a simple rule notation. The same notation is used to describe language syntax and semantics, with the accompanying text always explaining what is described. The following example shows the form:

-   rule-name:

    -   **literalstring1**

        **literalstring2** [ optional-section ]

    optional-section:

    -   **literalstring3**

Here, "rule-name" and "optional-section" describe rules, each of which can be expanded in a particular way. Expanding a rule means substituting one of the options of the rule into the place the rule is used. In the example, "optional-section" can be expanded into "literalstring3" or, in "rule-name", "optional-section" can also be substituted for nothing, as it is declared optional by the square brackets. Wherever "rule-name" is required, it can be substituted for either of the options declared in "rule-name". Anything highlighted, such as all **literalstrings** here are not rules, and thus cannot be expanded. 

Example code is shown as follows. Example code will always be valid Vala code, but will not necessarily be usable out of context.

```vala
class MyClass : Object {
	int field = 1;
}
        
```

Some phrases are used in a specific ways in this documentation and it is often useful to recognise their precise meanings: that is, to create a method, you write a declaration for it. When the program is running and the method exists, it is then defined as per your declaration and can be invoked.

