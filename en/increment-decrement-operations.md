

Increment/decrement operations
==============================

-   postfix-expression:

    -   primary-expression **++**

    -   primary-expression **--**

    prefix-expression:

    -   **++** unary-expression

    -   **--** unary-expression

Postfix and prefix expressions:

```vala
var postfix = i++;
var prefix = --j;
```     

are equivalent to:

```vala
var postfix = i;
i += 1;
j -= 1;
var prefix = j;
```
            

