# Documentation Conventions
Sections of this document describe the language using a simple rule notation. This notation is used to describe language syntax and semantics. These are explained in more detail by the accompanying text. The following example shows the form:

-   rule-name:

    -   **literalstring1**

    -    **literalstring2** [ optional-section ]

-   optional-section:

    -   **literalstring3**

Here, "rule-name" and "optional-section" describe rules, each of which can be expanded in a particular way. Expanding a rule means substituting one of the options of the rule into the place the rule is used. In the example, "optional-section" can be expanded into "literalstring3". In "rule-name", "optional-section" can be substituted for nothing, as it is declared optional by the square brackets. Wherever "rule-name" is required, it can be substituted for either of the options declared in "rule-name". Anything highlighted, such as all **literalstrings** here are not rules, and thus cannot be expanded. 

Code examples will be shown as follows. Example code will always be valid, but will not necessarily be usable out of context.

```vala
class MyClass : Object {
	int field = 1;
}
```
Some phrases are used in a specific ways in this document, please refer to the [Glossary](GLOSSARY.md) for their canonical definitions.