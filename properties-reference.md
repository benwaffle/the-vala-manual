

Properties Reference
====================

The format for the entries will be like so

  ---------- -------------------------------------- ----------------------- ----------------------------
  **Name**   **Applies To**                         **Values**              **Description**
  `foobar`   Signal, Function, Class, Struct, etc   The acceptable values   The description goes here.
  ---------- -------------------------------------- ----------------------- ----------------------------

And in alphabetical order:

  ------------------ ------------------ ------------------ ------------------
  **Name**           **Applies To**     **Values**         **Description**

  `abstract`         Class, Function    0, 1               

  `accessor_method`  Property           0, 1               

  `array_length_cnam Field              C identifier       
  e`                                                       

  `array_length_pos` Parameter          Double (position   Sets the position
                     (Function)         between two Vala   of the length for
                                        parameters)        the parameter,
                                                           length needs to be
                                                           hidden separately.

  `array_length_type Parameter          C type             
  `                  (Function),                           
                     Function                              
                     (returning an                         
                     array), Field                         

  `array_null_termin Function           0, 1               
  ated`              (returning an                         
                     array), Parameter                     
                     (Function), Field                     

  `async`            Function           0, 1               Force async
                                                           function, even if
                                                           it doesn't end in
                                                           \_async

  `base_class`       Class              C type             Marks the base
                                                           class for the type

  `base_type`        Struct             Vala type          Marks the struct
                                                           as inheriting

  `cheader_filename` Anything (except   Header include     Compiler will adds
                     parameters)        path               the specified
                                                           header when thing
                                                           is used.

  `common_prefix`    Enum               String             Removes a common
                                                           prefix from
                                                           enumeration values

  `const_cname`      Class              C type             
                     (non-GObject)                         

  `copy_function`    Class              C function name    
                     (non-GObject)                         

  `cprefix`          Module             String             

  `ctype`            Parameter          C type             
                     (Function), Field                     

  `default_value`    Parameter          Any Vala value     Sets the default
                     (Function)         that would be      value for a
                                        valid for the type parameter.

  `delegate_target_p Parameter          Double (position   
  os`                (Function)         between two Vala   
                                        parameters)        

  `deprecated`       Anything (except   0, 1               Marks the thing as
                     parameters)                           deprecated

  `deprecated_since` Anything (except   Version            Marks the thing as
                     parameters)                           deprecated

  `ellipsis`         Function           0, 1               Marks that the
                                                           function has a
                                                           variable argument
                                                           list

  `errordomain`      Enum               0, 1               Marks the
                                                           enumeration as a
                                                           GError domain

  `finish_name`      Function           C function name    Sets custom
                                                           asynchronous
                                                           finish function

  `free_function`    Class              C function name    Sets a free
                     (non-GObject)                         function for the
                                                           struct

  `gir_namespace`    Module             String             

  `gir_version`      Module             Version            

  `has_copy_function Struct             0, 1               marks the struct
  `                                                        as having a copy
                                                           function

  `has_destroy_funct Struct             0, 1               
  ion`                                                     

  `has_emitter`      Signal             0, 1               

  `has_target`       Delegate           0, 1               

  `has_type_id`      Class, Enum,       0, 1               Marks whether a
                     Struct                                GType is
                                                           registered for
                                                           this thing

  `hidden`           Anything           0, 1               Causes the
                                                           selected thing to
                                                           not be output in
                                                           the vapi file.

  `immutable`        Struct             0, 1               Marks the struct
                                                           as immutable

  `instance_pos`     Delegate           Double (Position   
                                        between two Vala   
                                        parameters)        

  `is_array`         Function           0, 1               Marks the thing as
                     (returning an                         an array
                     array), Parameter,                    
                     Field                                 

  `is_fundamental`   Class              0, 1               
                     (non-GObject)                         

  `is_immutable`     Class              0, 1               
                     (non-GObject)                         

  `is_out`           Parameter          0, 1               Marks the
                                                           parameter as "out"

  `is_ref`           Parameter          0, 1               Marks the
                                                           parameter as "ref"

  `is_value_type`    Struct, Union      0, 1               Marks type as a
                                                           value type (aka
                                                           struct)

  `lower_case_cprefi Module             String             
  x`                                                       

  `lower_case_csuffi Interface          String             
  x`                                                       

  `name`             Any Type,          Vala identifier    Changes the name
                     Function, Signal                      of the thing, does
                                                           not change
                                                           namespace

  `namespace`        Any Type           String             Changes the
                                                           namespace of the
                                                           thing

  `namespace_name`   Signal Parameter   String             Specify the
                                                           namespace of the
                                                           parameter type
                                                           indicated with
                                                           type\_name

  `no_array_length`  Function           0, 1               Does not
                     (returning an                         implicitly
                     array), Parameter                     pass/return array
                     (Function,                            length to/from
                     Delegate)                             function

  `nullable`         Function (having a 0, 1               Marks the value as
                     return value),                        nullable
                     Parameter                             

  `owned_get`        Property           0, 1               

  `parent`           Any module member  String (Namespace) Strip namespace
                                                           prefix from symbol
                                                           and put it into
                                                           given
                                                           sub-namespace

  `printf_format`    Function           0, 1               

  `rank`             Struct             Integer            

  `ref_function`     Class              C function name    
                     (non-GObject)                         

  `ref_function_void Class              0, 1               
  `                  (non-GObject)                         

  `rename_to`        Any Type           Vala identifier    Renames the type
                                                           to something else,
                                                           ie fooFloat to
                                                           float (not exactly
                                                           the same as `name`
                                                           , AFAIK name
                                                           changes both the
                                                           vala name and the
                                                           cname. rename\_to
                                                           adds the required
                                                           code so that when
                                                           the rename\_to'ed
                                                           type is used, the
                                                           c type is used)

  `replacement`      Anything (except   The thing that     Specifies a
                     parameters)        replaces this      replacement for a
                                                           deprecated symbol

  `sentinel`         Function (with     C value            The sentinel value
                     ellipsis)                             marking the end of
                                                           the vararg list

  `simple_type`      Struct             0, 1               Marks the struct
                                                           as being a simple
                                                           type, like int

  `takes_ownership`  Parameter          0, 1               
                     (Function,                            
                     Delegate)                             

  `throws`           Function           0, 1               Marks that the
                                                           function should
                                                           use an out
                                                           parameter instead
                                                           of throwing an
                                                           error

  `to_string`        Enum               C function name    

  `transfer_ownershi Function/Delegate/ 0, 1               Transfers
  p`                 Signal                                ownership of the
                     (having a return                      value
                     value), Parameter                     
                     (Function, Signal)                    

  `type_arguments`   Function/Delegate/ Vala types, comma  Restricts the
                     Signal             separated          generic type of
                     (having a return                      the thing
                     value), Property,                     
                     Field, Parameter                      

  `type_check_functi Class (GObject)    C function/macro   
  on`                                   name               

  `type_id`          Struct, Class      C macro            
                     (GObject)                             

  `type_name`        Function (having a Vala type name     Changes the type
                     return value),                        of the selected
                     Property,                             thing. Overwrites
                     Parameter, Field                      old type, so
                                                           "type\_name" must
                                                           be before any
                                                           other type
                                                           modifying metadata

  `type_parameters`  Delegate, Class    Vala generic type  
                     (non-GObject)      parameters, e.g.   
                                        T, comma separated 

  `unref_function`   Class              C function name    
                     (non-GObject)                         

  `value_owned`      Parameter          0, 1               
                     (Function)                            

  `vfunc_name`       Function           C function pointer 
                                        name               

  `virtual`          Function           0, 1               

  `weak`             Field              0, 1               Marks the field as
                                                           weak
  ------------------ ------------------ ------------------ ------------------

