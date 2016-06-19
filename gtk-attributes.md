<div id="gtk-attributes" class="section level1">

Gtk attributes
==============

**GtkTemplate attribute**

Can only be applied to classes that inherit from Gtk.Widget. The "ui"
argument is mandatory.

  ------------------------ ------------------------ ------------------------
  **Name**                 **Type**                 **Example**

  **Description                                     
  (optional)**                                      

  ui                       string (mandatory)       "/org/gnome/yourapp/main
                                                    .ui"

  Specifies the .ui                                 
  gresource to be used for                          
  building the Gtk widget                           
  ------------------------ ------------------------ ------------------------

**GtkChild attribute**

Can only be applied to fields of classes being marked with
[GtkTemplate]. It's used to connect a field with a child object in the
Gtk builder definition.

  ------------------------ ------------------------ ------------------------
  **Name**                 **Type**                 **Example**

  **Description                                     
  (optional)**                                      

  name                     string                   

  Custom name being used                            
  in the Gtk builder ui                             
  definition. By default                            
  the name of the marked                            
  field is used.                                    

  internal                 bool                     

  Whether this child is                             
  internal or not in the                            
  Gtk builder ui                                    
  definition.                                       
  ------------------------ ------------------------ ------------------------

**GtkCallback attribute**

Can only be applied to methods of classes being marked with
[GtkTemplate]. It's used to connect to a signal defined in the Gtk
builder ui with the marked method.

  ------------------------ ------------------------ ------------------------
  **Name**                 **Type**                 **Example**

  **Description                                     
  (optional)**                                      

  name                     string                   "on\_button\_clicked"

  Custom name being used                            
  in the Gtk builder ui                             
  definition. By default                            
  the name of the marked                            
  method is used.                                   
  ------------------------ ------------------------ ------------------------

</div>
