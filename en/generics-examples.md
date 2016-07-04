Examples
========
```vala
public interface With < T > {

	public abstract void sett(T t);

	public abstract T gett();

}

public class One : Object, With < int > {
	public int t;

	public void sett(int t) {
		this.t = t;
	}

	public int gett() {
		return t;
	}
}

public class Two < T, U > : Object, With < T > {
	public T t;

	public void sett(T t) {
		this.t = t;
	}

	public T gett() {
		return t;
	}

	public U u;
}

public class Test : Object {

	public static void main(string[] args) {

		var o = new One ();

		o.sett(5);

		stdout.printf("%d", o.t);

		var t = new Two < int, double > ();

		t.sett(5);

		stdout.printf("%d", t.t);

		t.u = 5.0f;

		stdout.printf("%f", t.u);

	}
}
```
