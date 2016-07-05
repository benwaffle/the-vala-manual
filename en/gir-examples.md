# Examples

## Overriding Types

When you have the following expression:

`typedef GList MyList;`

where GList will hold integers, use type metadata as follows:

`MyList type="GLib.List<int>"`

The above metadata will generate the following code:
```vala
public class MyList : GLib.List<int> {
    [CCode (has_construct_function = false)]
    protected MyList ();
    public static GLib.Type get_type ();
}
```
Then you can use GLib.List or NameSpace.MyList as if equal.

## Skipping Symbols

`MySymbol skip`
