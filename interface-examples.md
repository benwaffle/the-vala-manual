Examples
========

Here is an example implementing (and overriding) an *abstract* interface method,

 ```vala
/* 
This example gives you a simple interface, Speaker, with - one abstract method, speak
 
 
It shows you three classes to demonstrate how these and overriding them behaves:

- Fox, implementing Speaker
- ArcticFox, extending Fox AND implementing Speaker (ArcticFox.speak () replaces superclasses' .speak())
- RedFox, extending Fox BUT NOT implementing speaker (RedFox.speak () does not replace superclasses' .speak())
 
Important notes:

- generally an object uses the most specific class's implementation
- ArcticFox extends Fox (which implements Speaker) and implements Speaker itself, 
- ArcticFox defines speak () with new, so even casting to Fox or Speaker still gives you ArcticFox.speak ()
- RedFox extends from Fox, but DOES NOT implement Speaker
- RedFox speak () gives you RedFox.speak ()
- casting RedFox to Speaker or Fox gives you Fox.speak ()

*/     
 
 
/* Speaker: extends from GObject */
interface Speaker : Object {
	/* speak: abstract without a body */
	public abstract void speak ();
}
 
 
/* Fox: implements Speaker, implements speak () */
class Fox : Object, Speaker {
	public void speak () {
		stdout.printf ("  Fox says Ow-wow-wow-wow\n");
	}
}
 
 
/* ArcticFox: extends Fox; must also implement Speaker to re-define
*  inherited methods and use them as Speaker */
class ArcticFox : Fox, Speaker {
	/* speak: uses 'new' to replace speak () from Fox */
	public new void speak () {
		stdout.printf ("  ArcticFox says Hatee-hatee-hatee-ho!\n");
	}
}
 
 
/* RedFox: extends Fox, does not implement Speaker */
class RedFox : Fox {
	public new void speak () {
		stdout.printf ("  RedFox says Wa-pa-pa-pa-pa-pa-pow!\n");
	}
}
 
 
public static int main () {
	Speaker f = new Fox ();
	Speaker a = new ArcticFox ();
	Speaker r = new RedFox ();
	 
	 
	stdout.printf ("\n\n// Fox implements Speaker, speak ()\n");
	stdout.printf ("Fox as Speaker:\n");
	(f as Speaker).speak ();   /* Fox.speak () */
	stdout.printf ("\nFox as Fox:\n");
	(f as Fox).speak ();       /* Fox.speak () */
	 
	 
	stdout.printf ("\n\n// ArcticFox extends Fox, re-implements Speaker and " + "replaces speak ()\n");
	stdout.printf ("ArcticFox as Speaker:\n");
	(a as Speaker).speak ();   /* ArcticFox.speak () */
	stdout.printf ("\nArcticFox as Fox:\n");
	(a as Fox).speak ();       /* ArcticFox.speak () */
	stdout.printf ("\nArcticFox as ArcticFox:\n");
	(a as ArcticFox).speak (); /* ArcticFox.speak () */
	 
	 
	stdout.printf ("\n\n// RedFox extends Fox, DOES NOT re-implement Speaker but" + " does replace speak () for itself\n");
	stdout.printf ("RedFox as Speaker:\n");
	(r as Speaker).speak ();   /* Fox.speak () */
	stdout.printf ("\nRedFox as Fox:\n");
	(r as Fox).speak ();       /* Fox.speak () */
	stdout.printf ("\nRedFox as RedFox:\n");
	(r as RedFox).speak ();    /* RedFox.speak () */
	 
	 
	return 0;
}
```

Here is an example of implementing (and inheriting) a *virtual*
interface method. Note that the same rules for subclasses re-implementing methods that apply to the *abstract* interface method above apply here.

```vala
/* 
This example gives you a simple interface, Yelper, with- one virtual default method, yelp

It shows you two classes to demonstrate how these and overriding them behaves:

- Cat, implementing Yelper (inheriting yelp)
- Fox, implementing Yelper (overriding yelp)
 
Important notes:
- generally an object uses the most specific class's implementation
- Yelper provides a default yelp (), but Fox overrides it
- Fox overriding yelp () means that even casting Fox to Yelper still gives you Fox.yelp ()
- as with the Speaker/speak() example, if a subclass wants to override an implementation (e.g. Fox.yelp ()) of a virtual interface method (e.g. Yelper.yelp ()), it must use 'new' 
- 'override' is used when overriding regular class virtual methods, but not when implementing interface virtual methods.
*/     
 
 
interface Yelper : Object {
	/* yelp: virtual, if we want to be able to override it */
	public virtual void yelp () {
		stdout.printf ("  Yelper yelps Yelp!\n");
	}
}
 
 
/* Cat: implements Yelper, inherits virtual yelp () */
class Cat : Object, Yelper {
}
 
 
/* Fox: implements Yelper, overrides virtual yelp () */
class Fox : Object, Yelper {
	public void yelp () {
		stdout.printf ("  Fox yelps Ring-ding-ding-ding-dingeringeding!\n");
	}
}
 
 
public static int main () {
	Yelper f = new Fox ();
	Yelper c = new Cat ();
	 
	 
	stdout.printf ("// Cat implements Yelper, inherits yelp\n");
	stdout.printf ("Cat as Yelper:\n");
	(c as Yelper).yelp ();  /* Yelper.yelp () */
	stdout.printf ("\nCat as Cat:\n");
	(c as Cat).yelp ();     /* Yelper.yelp () */
	 
	 
	stdout.printf ("\n\n// Fox implements Yelper, overrides yelp ()\n");
	stdout.printf ("Fox as Yelper:\n");
	(f as Yelper).yelp ();  /* Fox.yelp () */
	stdout.printf ("\nFox as Fox:\n");
	(f as Fox).yelp ();     /* Fox.yelp () */
	 
	 
	return 0;
}

```