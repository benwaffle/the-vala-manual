<div id="incrementdecrement-operations" class="section level1">

Increment/decrement operations
==============================

-   postfix-expression:

    -   primary-expression **++**

        primary-expression **--**

    prefix-expression:

    -   **++** unary-expression

        **--** unary-expression

Postfix and prefix expressions:

              var postfix = i++;
                       var prefix = --j;
            

are equivalent to:

              var postfix = i;
                       i += 1;
              
              
                       j -= 1;
                       var prefix = j;
            

</div>