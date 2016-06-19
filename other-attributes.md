<div id="other-attributes" class="section level1">

Other attributes
================

  ------------------------ ------------------------ ------------------------
  **Name**                 **Applies to**           **Description**

  Assert                   method                   

  Compact                  class                    

  ConcreteAccessor         abstract property        Use get/set functions,
                                                    but do not override them
                                                    as they are not
                                                    abstract.

  DestroysInstance         method                   

  Diagnostics              method                   

  ErrorBase                class                    Only use by GLib.Error
                                                    at the moment

  Experimental                                      

  Flags                    enum                     Marks the enum values to
                                                    be flags

  HasEmitter               signal                   

  Immutable                class, struct            

  ModuleInit               method                   Marks the associated
                                                    type as dynamic, and
                                                    marks the method as a
                                                    [TypeModule](http://vala
                                                    doc.org/#!api=gobject-2.
                                                    0/GLib.TypeModule)
                                                    init function. See
                                                    [TypeModule
                                                    example](http://wiki.gno
                                                    me.org/action/show/Proje
                                                    cts/Vala/Manual/Export/P
                                                    rojects/Vala/TypeModuleS
                                                    ample#)

  NoAccessorMethod         property                 

  NoArrayLength            method                   Deprecated, use
                                                    `[CCode (array_length = 
                                                    false)]`
                                                    instead

  NoReturn                 method                   Once the method is
                                                    called, it will never
                                                    return

  NoThrow                  method                   Marks methods that can
                                                    never throw exceptions.
                                                    Dova profile only

  NoWrapper                method                   

  PointerType                                       

  Print                    method                   Stringifies and
                                                    concatenates all
                                                    arguments you pass to
                                                    the method

  PrintfFormat             method                   See also ScanfFormat
                                                    attribute

  ReturnsModifiedPointer   method                   

  ScanfFormat              method                   See also PrintFormat
                                                    attribute

  ThreadLocal              field                    Thread local fields.
                                                    Dova profile only
  ------------------------ ------------------------ ------------------------

</div>
