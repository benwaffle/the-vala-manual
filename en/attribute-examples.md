# Examples

### Gtk Attributes

This example shows how to use the Gtk attributes to automatically bind a Glade XML representation of UI to a Vala Class. While it would be possible to do this on the command line in several steps, a Makefile is used to automate the process.

mywidget.vala
```vala
using Gtk;

[GtkTemplate (ui = "/org/foo/my/mywidget.ui")]
public class MyWidget : Box {
	public string text {
		get { return entry.text; }
		set { entry.text = value; }
	}

	[GtkChild]
	private Entry entry;

	public MyWidget (string text) {
		this.text = text;
	}

	[GtkCallback]
	private void on_button_clicked (Button button) {
		print ("The button was clicked with entry text: %s\n", entry.text);
	}

	[GtkCallback]
	private void on_entry_changed (Editable editable) {
		print ("The entry text changed: %s\n", entry.text);

		notify_property ("text");
	}
}

void main(string[] args) {
	Gtk.init (ref args);
	var win = new Window();
	win.destroy.connect (Gtk.main_quit);

	var widget = new MyWidget ("The entry text!");

	win.add (widget);
	win.show_all ();

	Gtk.main ();
}
```

mywidget.ui

```xml
<?xml version="1.0" encoding="UTF-8"?>
<interface>
  <!-- interface-requires gtk+ 3.8 -->
  <template class="MyWidget" parent="GtkBox">
    <property name="visible">True</property>
    <property name="can_focus">False</property>
    <property name="orientation">vertical</property>
    <property name="spacing">4</property>
    <child>
      <object class="GtkLabel" id="label1">
        <property name="visible">True</property>
        <property name="can_focus">False</property>
        <property name="halign">start</property>
        <property name="valign">start</property>
        <property name="xalign">0</property>
        <property name="label" translatable="yes">This widget is defined with composite GtkBuilder script</property>
        <property name="wrap">True</property>
      </object>
      <packing>
        <property name="expand">False</property>
        <property name="fill">True</property>
        <property name="position">0</property>
      </packing>
    </child>
    <child>
      <object class="GtkEntry" id="entry">
        <property name="visible">True</property>
        <property name="can_focus">True</property>
        <property name="invisible_char">•</property>
        <signal name="changed" handler="on_entry_changed" object="MyWidget" swapped="no"/>
      </object>
      <packing>
        <property name="expand">False</property>
        <property name="fill">True</property>
        <property name="position">1</property>
      </packing>
    </child>
    <child>
      <object class="GtkLabel" id="label2">
        <property name="visible">True</property>
        <property name="can_focus">False</property>
        <property name="halign">start</property>
        <property name="valign">start</property>
        <property name="xalign">0</property>
        <property name="label" translatable="yes">Press the button to fetch the internal entry text</property>
        <property name="wrap">True</property>
      </object>
      <packing>
        <property name="expand">False</property>
        <property name="fill">True</property>
        <property name="position">2</property>
      </packing>
    </child>
    <child>
      <object class="GtkButton" id="button">
        <property name="label" translatable="yes">The Button</property>
        <property name="visible">True</property>
        <property name="can_focus">True</property>
        <property name="receives_default">True</property>
        <property name="halign">end</property>
        <signal name="clicked" handler="on_button_clicked" swapped="no"/>
      </object>
      <packing>
        <property name="expand">False</property>
        <property name="fill">True</property>
        <property name="position">3</property>
      </packing>
    </child>
  </template>
</interface>
```
my-resources.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<gresources>
  <gresource prefix="/org/foo/my">
    <file compressed="true" preprocess="xml-stripblanks">mywidget.ui</file>
  </gresource>
</gresources>
```
Makefile
```make
VALAC=valac

all: demo

clean:
	rm -fv *~ *.o demo my-resources.c mywidget.c

my-resources.c: my-resources.xml mywidget.ui
	glib-compile-resources my-resources.xml \
		--target=$@ --sourcedir=$(srcdir) --c-name _my --generate-source

mywidget.c:mywidget.vala
	$(VALAC) -C $< --pkg gtk+-3.0 --target-glib=2.38 --gresources my-resources.xml

%.o:%.c
	gcc -o $@ -c $< -Wall `pkg-config --cflags gtk+-3.0 gmodule-export-2.0`

demo: mywidget.o my-resources.o
	gcc -o $@  $^ `pkg-config --libs gtk+-3.0 gmodule-export-2.0`
```