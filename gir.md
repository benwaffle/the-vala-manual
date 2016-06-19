GIR metadata format
-------------------

The `GIR` format actually has a lot of information for generating bindings, but it's a different language than Vala. Therefore, it's almost impossible to directly map a whole .gir file into a Vala tree, hence the need of metadata. On the other side we might want to use directly .gir + .metadata instead of generating a .vapi, but .vapi is more humanly readable and faster to parse than the GIR, hence the need of vapigen for generating a .vapi.


