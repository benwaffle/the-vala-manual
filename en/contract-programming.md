

Contract programming
====================

requires ( ... ) Denotes things that must be true to start execution.

ensures ( ... ) Denotes things that must be true to end execution.

```vala
double method_name(int x, double d)
        requires (x > 0 && x < 10)
        requires (d >= 0.0 && d <= 1.0)
        ensures (result >= 0.0 && result <= 10.0)
{
    return d * x;
}
```