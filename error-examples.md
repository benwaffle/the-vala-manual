Examples
========

Demonstrating...

```vala

errordomain ErrorType1 {
	CODE_1A
}

errordomain ErrorType2 {
	CODE_2A
}

public class Test : GLib.Object {

	public static void thrower() throws ErrorType1, ErrorType2 {
		throw new ErrorType2.CODE_1A("Error");
	}

	public static void catcher() throws ErrorType2 {
		try {
			thrower();
		} catch (ErrorType1 ex) {
			// Deal with ErrorType1
		} finally {
			// Tidy up
		}
	}

	public static void main(string[] args) {
		try {
			catcher();
		} catch (ErrorType2 ex) {
			// Deal with ErrorType2
		}
	}
}       
```