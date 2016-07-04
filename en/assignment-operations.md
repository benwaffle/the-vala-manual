

Assignment operations
=====================

Value assigned to identifier on left. Type must match.

When assignment includes another operation natural result type must match the declared type of variable which is the left hand side of the expression. e.g. Let a be an int instance with the value 1, a += 0.5 is not allowed, as the natural result type of 1 + 0.5 is a float, not an int.

-   assignment-expression:

    -   simple-assignment-expression

    -   number-assignment-expression

-   simple-assignment-expression:

    -   conditional-expression **=** expression

-   number-assignment-expression:

    -   conditional-expression **+=** expression

    -   conditional-expression **-=** expression

    -   conditional-expression **\*=** expression

    -   conditional-expression **=** expression

    -   conditional-expression **%=** expression

    -   conditional-expression **|=** expression

    -   conditional-expression **&=** expression

    -   conditional-expression **^=** expression

    -   conditional-expression **<<=** expression

    -   conditional-expression **\>\>=** expression

A simple assignment expression assigns the right handed side value to the left handed side. It is necessary that the left handed side expression is a valid lvalue. Other assignments:

```vala
result += value;
result <<= value;
```

Are equivalent to simple assignments:
```vala
result = result + value;
result = result << value;
```     
