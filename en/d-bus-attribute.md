

DBus Attribute
==============

This attribute influences the generation of DBus interfaces (for servers) or DBus calls (for clients) which are generated by Vala.

| Name | Applies to | Type | Example | Description (optional) |
| --- | --- | --- | --- | --- |
| name | class, interface,method, property,signal | string | "org.my.interface" or "MyMember" | |
| signature| class, interface,method, property,signal |string | | This makes it possible to use GVariant in D-Bus clients and   servers without automatic     boxing/unboxing. |
| use\_string\_marshalling | enum | bool | | Marshalling enum  values as strings |
| value | enum	| value | string | Marshalling enum values as strings |
| use\_string\_marshalling | enum | bool | | |
| timeout | method, property | integer | | Client only. Timeout is specified in  milliseconds |
| no\_reply | method | | | Do not expect a reply from the  server |
| result | method | string | | Server only |
| visible | method, property,signal | bool | | Server only. By setting `visible = false` you can specify that the member should not be exported via D-Bus |
