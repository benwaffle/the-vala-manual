

Valid arguments
===============

|Name|Applies to|Type|Description|
|---|---|---|---|
|skip|all|bool|Skip processing the symbol|
|hidden|all|bool|Process the symbol but hide from output|
|type|method, parameter, property, field, constant, alias|string|Complete Vala type|
|type\_arguments|method, parameter, property, field, constant, alias|string|Vala type parameters for generics, separated by commas|
|cheader\_filename|all including namespace|string|C headers separated by commas|
|name|all including namespace|string|Vala symbol name|
|owned|parameter|bool|Whether the parameter value should be owned|
|unowned|method, property, field, constant|bool|Whether the symbol is unowned|
|parent|all|string|Move the symbol to the specified container symbol. If no container exists, a new namespace will be created.|
|nullable|method, parameter, property, field, constant, alias|bool|Whether the type is nullable or not|
|deprecated|all|bool|Whether the symbol is deprecated or not|
|replacement|all|string|Deprecation replacement, implies `deprecated=true`|
|deprecated\_since|all|string|Deprecated since version, implies `deprecated=true`|
|array|method, parameter, property, field, constant, alias|bool|Whether the type is an array or not|
|array\_length\_idx|parameter|int|The index of the C array length parameter|
|default|parameter|any|Default expression for the parameter|
|out|parameter|bool|Whether the parameter direction is out or not|
|ref|parameter|bool|Whether the parameter direction is ref or not|
|vfunc\_name|method|string|Name of the C virtual function|
|virtual|method, signal, property|bool|Whether the symbol is virtual or not|
|abstract|method, signal, property|bool|Whether the symbol is abstract or not|
|scope|parameter (async method)|string|Scope of the delegate, in GIR terms|
|struct|record (detected as boxed compact class)|bool|Whether the boxed type must be threaten as struct instead of compact class|
|printf\_format|method|bool|Add the [PrintfFormat] attribute to the method if true|
|array\_length\_field|field (array)|string|The name of the length field|
|sentinel|method|string|C expression of the last argument for varargs|
|closure|parameter|int|Specifies the index of the parameter representing the user data for this callback|
|errordomain|enumeration|bool|Whether the enumeration is an errordomain or not|
|destroys\_instance|method|bool|Whether the instance is owned by the method|
|throws|method|string|Type of exception the method throws|

